---
name: devops-conventions
description: Use when writing content about Kubernetes, AWS, Terraform, ArgoCD, Vault, Istio, or any tool in the DevOps program. Ensures technical accuracy, correct versions, and alignment with the author's real production environment.
---

# DevOps Conventions Skill

## Stack de referencia (entorno real del autor)

Siempre usar estas versiones cuando se documente o ejemplifique:

| Herramienta | Versión en uso | Notas |
|-------------|---------------|-------|
| EKS | 1.35.4-eks | arm64, Karpenter, On-Demand |
| ArgoCD | v2.14.10 | GitOps multi-env |
| Karpenter | 1.6.0 | Reemplaza nodegroups |
| Istio | 1.25.0 | mTLS strict mode |
| Vault | 0.29.1 | Integración KMS |
| External Secrets Operator | 0.14.4 | |
| Crossplane | 1.19.0 | |
| Terraform | latest (workspace-based) | AWS provider |
| kubectl | v1.35.x | (actualizar desde v1.29) |
| Helm | 3.x | |
| ALB Controller | 1.13.4 | |
| Argo Rollouts | 2.40.2 | |
| VictoriaMetrics | stack completo | Reemplaza Prometheus |
| Loki | stack completo | |

## Convenciones por tecnología

### Kubernetes / CKA

Para los labs de CKA usar clusters `kubeadm`, NO EKS:
- EKS es managed — no permite acceder al control plane
- El examen CKA usa clusters kubeadm vanilla
- Los labs de EKS van bajo `labs/eks/`, separados de los labs de CKA

Alias obligatorios para cualquier ejemplo de kubectl:
```bash
alias k=kubectl
export do="--dry-run=client -o yaml"
export now="--force --grace-period 0"
```

Formato estándar de un manifiesto de ejemplo:
```yaml
apiVersion: v1
kind: Pod
metadata:
  name: ejemplo
  namespace: default
  labels:
    app: ejemplo
spec:
  containers:
  - name: nginx
    image: nginx:1.25-alpine   # Siempre usar imagen con tag, nunca :latest
    resources:
      requests:
        cpu: "100m"
        memory: "128Mi"
      limits:
        cpu: "200m"
        memory: "256Mi"
```

### Terraform / HCL

Estructura de módulo estándar:
```
module/
├── main.tf
├── variables.tf
├── outputs.tf
├── versions.tf
└── README.md
```

Siempre declarar el provider con versión mínima:
```hcl
terraform {
  required_version = ">= 1.6.0"
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "~> 5.0"
    }
  }
}
```

Usar `AWS_PROFILE` en lugar de hardcodear profiles en `provider.tf`:
```bash
export AWS_PROFILE=plat-dev
terraform plan
```

### ArgoCD / GitOps

Estructura de referencia de los repos de GitOps:
- `argocd-deploy-non-prod` → carpeta `inno/plat/use1-dev/`
- `argocd-deploy-prod`

Siempre documentar el estado de las apps con los campos reales:
```
Health Status: Healthy / Degraded / Unknown
Sync Status: Synced / OutOfSync / Unknown
```

Los hallazgos de la migración DEV se referencian como:
- **H-01** — ArgoCD Unknown (EKS 1.35 `terminatingReplicas` incompatibilidad)
- **H-02** — ALB Controller OutOfSync (9 servicios 404)
- **H-03** — admin-portal / da-bi-tempdash / landing-page Degraded
- **H-04** — 5 apps OutOfSync
- **H-05** — kubectl client v1.29 vs server 1.35 (version skew)

Usar estos como ejemplos reales en los módulos de troubleshooting.

### AWS

Cuentas de referencia (nunca poner IDs en documentación pública):
- `plat-dev` — entorno de desarrollo y validación
- `plat-staging` — staging
- `plat-prod` — producción
- `core-dns` — Route53 / `zensy-aws.net`
- `core-network` — Transit Gateway

VPCs:
- dev: `10.2.0.0/16`
- staging: `10.1.0.0/16`
- prod: `10.0.0.0/16`

SSO: siempre usar `aws sso login --profile <nombre>` con perfil definido en `~/.aws/config`.

### Vault

Integración estándar con Kubernetes:
```yaml
# External Secret referenciando Vault
apiVersion: external-secrets.io/v1beta1
kind: ExternalSecret
metadata:
  name: ejemplo-secret
spec:
  secretStoreRef:
    name: vault-backend
    kind: ClusterSecretStore
  target:
    name: ejemplo-secret
  data:
  - secretKey: password
    remoteRef:
      key: secret/data/app/ejemplo
      property: password
```

## Errores comunes a evitar

- ❌ Usar `:latest` en imágenes de contenedor en ejemplos
- ❌ Documentar `ping` para health checks en AWS (ICMP bloqueado en ALBs)
- ❌ Hardcodear AWS Account IDs o credenciales en ejemplos
- ❌ Mezclar labs de `kubeadm` y EKS en el mismo laboratorio
- ❌ Usar `kubectl delete pod X --force` sin explicar las consecuencias
- ❌ Documentar comandos sin verificar que funcionan en la versión indicada

## Health checks correctos en AWS

```bash
# ✅ Correcto: curl con código de estado
curl -sI https://servicio.ejemplo.com | head -1

# ✅ Correcto: verificar con código de retorno
curl -o /dev/null -w "%{http_code}" https://servicio.ejemplo.com

# ❌ Incorrecto: ping a un ALB (siempre timeout)
ping alb-xxx.us-east-1.elb.amazonaws.com
```
