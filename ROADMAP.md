# 🗺️ ROADMAP — DevOps Engineer Professional Program

> Versión: 1.0 | Duración: 12 meses | Inicio: julio 2026

---

## Principios del programa

1. **Certificaciones fuertes antes que muchas** — 6 certificaciones estratégicas valen más que 90 cursos de Udemy
2. **Evidencia real antes que proyectos inventados** — documentar trabajo de producción sanitizado (Zensy → runbooks públicos) es más valioso que ejercicios de tutorial
3. **Sostenible sobre ambicioso** — el plan está calibrado para alguien con trabajo full-time, proyecto de migración activo y consultoría freelance en paralelo
4. **Cada módulo es independiente** — se puede actualizar, ampliar o reordenar sin romper el resto

---

## Vista anual

```
Mes  01-02  │ Base gratuita: Codefresh + OCI Foundations + perfil público
Mes  03-05  │ Terraform Associate + primer proyecto público
Mes  06-09  │ CKA (bloque principal) + Vault Associate
Mes  10-12  │ AWS Solutions Architect Associate
```

---

## Detalle por fase

---

### Fase 0 — Preparación (semanas 1-2)

**Objetivo:** dejar lista la infraestructura del programa antes de estudiar.

- [ ] Crear repositorio `devops-professional-program` en GitHub
- [ ] Configurar estructura de carpetas
- [ ] Crear `PROGRESS.md` con template semanal
- [ ] Actualizar LinkedIn (headline, experiencia actual, skills)
- [ ] Identificar horas de estudio disponibles por semana (objetivo mínimo: 6-8h/semana)
- [ ] Revisar estado del inglés técnico (lectura de docs, nivel objetivo: B2 técnico)

---

### Fase 1 — Base gratuita (meses 1-2)

**Certificaciones:** Codefresh GitOps Fundamentals + Oracle OCI Foundations  
**Costo:** $0  
**Horas estimadas:** 30-40h

#### Semana 1-2: Codefresh GitOps

| Día | Actividad |
|-----|-----------|
| Lunes | Registrarse en Codefresh Academy, revisar temario completo |
| Martes-Miércoles | GitOps principles, Git-driven deployments, módulos 1-3 |
| Jueves-Viernes | ArgoCD fundamentals, ApplicationSets, Helm en ArgoCD |
| Fin de semana | Laboratorio: mapear lo aprendido con tu setup real en `argocd-deploy-non-prod` |

#### Semana 3-4: Codefresh — parte 2 + examen

| Día | Actividad |
|-----|-----------|
| Lunes-Martes | Progressive delivery, Argo Rollouts, Argo Workflows |
| Miércoles-Jueves | Repaso general + práctica con simuladores |
| Viernes | **Examen Codefresh GitOps Fundamentals** |
| Fin de semana | Documentar lecciones en `modules/07-gitops-argocd.md` |

#### Semana 5-6: Oracle OCI Foundations

| Día | Actividad |
|-----|-----------|
| Lunes-Martes | OCI Architecture, IAM, Compute |
| Miércoles-Jueves | Networking (VCN, gateways, load balancers), Storage |
| Viernes | Databases, Security, Observability en OCI |
| Fin de semana | Laboratorio con Oracle Free Tier (cuenta gratuita) |

#### Semana 7-8: OCI Foundations — cierre + examen

| Día | Actividad |
|-----|-----------|
| Lunes-Martes | Repaso de servicios core, práctica con preguntas de muestra |
| Miércoles | Simulacro completo |
| Jueves | **Examen OCI Foundations** |
| Viernes | Inicio de `projects/01-migration-runbook/` — estructura base |
| Fin de semana | Documentar lecciones, actualizar `PROGRESS.md` |

**Entregables al cierre de Fase 1:**
- [x] Certificado Codefresh GitOps Fundamentals
- [x] Certificado OCI Foundations
- [x] LinkedIn actualizado con ambas certificaciones
- [x] Módulo `07-gitops-argocd.md` con apuntes propios

---

### Fase 2 — Terraform Associate (meses 3-5)

**Certificación:** HashiCorp Terraform Associate 003  
**Costo:** ~$70  
**Horas estimadas:** 60-80h

**Ventaja de tu perfil:** ya usás Terraform con AWS en producción (`plat-dev`, `plat-staging`). El tiempo de estudio es significativamente menor que para alguien que empieza desde cero.

#### Semana 9-10: Foundations repaso

- HCL syntax, tipos de datos, variables, outputs
- Providers, resources, data sources
- State: local vs remoto (S3 + DynamoDB como ya usás)
- Modules: estructura, reutilización

#### Semana 11-12: Intermediate

- Workspaces
- `terraform import`, `moved` blocks
- `terraform state` manipulación
- Testing: `terraform validate`, `terraform plan` en CI/CD
- Backends, locking

#### Semana 13-15: Laboratorio + proyecto público

- Laboratorio: levantar infraestructura real en `plat-dev` con un módulo Terraform propio
- **Proyecto público:** `projects/01-migration-runbook/` — runbook sanitizado de la migración lafue→nueva infra, documentando los patrones de Terraform usados (sin datos sensibles de Zensy)
- Agregar diagramas de arquitectura en `diagrams/`

#### Semana 16-17: Preparación examen

- Simulacros oficiales HashiCorp
- Revisar áreas de menor familiaridad (testing, sentinel, cloud agnostic patterns)
- Checklist de certificación en `certifications/terraform-associate.md`

#### Semana 18: Examen

- Revisar `certifications/terraform-associate.md` la noche anterior
- **Examen Terraform Associate**
- Actualizar LinkedIn y `PROGRESS.md`

**Entregables al cierre de Fase 2:**
- [x] Certificado Terraform Associate
- [x] Módulo `06-terraform.md` completo
- [x] Primer proyecto público publicado en GitHub
- [x] Certificación visible en LinkedIn

---

### Fase 3 — CKA (meses 6-9)

**Certificación:** Certified Kubernetes Administrator (CNCF)  
**Costo:** ~$445 (incluye un reintento)  
**Horas estimadas:** 120-150h — el bloque más extenso del programa

**Ventaja de tu perfil:** operás EKS 1.35 arm64 con Karpenter, Istio, ArgoCD en producción. Los laboratorios del examen son sobre `kubeadm` clusters, no EKS, así que hay que cubrir la brecha de administración de cluster "vanilla".

#### Dominios del examen (pesos oficiales)

| Dominio | Peso |
|---------|------|
| Cluster Architecture, Installation & Configuration | 25% |
| Workloads & Scheduling | 15% |
| Services & Networking | 20% |
| Storage | 10% |
| Troubleshooting | 30% |

> ⚠️ Troubleshooting pesa el 30% — no lo dejes para el final.

#### Semana 19-22: Foundations

- `kubeadm init`, join, upgrade de cluster
- ETCD backup y restore
- Componentes del control plane: kube-apiserver, scheduler, controller-manager, etcd
- RBAC: ClusterRole, Role, Bindings, ServiceAccounts
- Laboratorio: levantar cluster local con `kubeadm` en VMs (Multipass o Vagrant)

#### Semana 23-26: Workloads y Networking

- Deployments, DaemonSets, StatefulSets, Jobs, CronJobs
- Probes: liveness, readiness, startup
- Resource requests/limits, LimitRange, ResourceQuota
- Services: ClusterIP, NodePort, LoadBalancer, ExternalName
- Ingress, NetworkPolicies
- DNS interno: CoreDNS
- CNI: conceptos (no necesitás instalarlo desde cero pero sí entender qué hace)

#### Semana 27-30: Storage + Troubleshooting

- PV, PVC, StorageClass, dynamic provisioning
- Volumes: emptyDir, hostPath, configMap, secret
- Troubleshooting pods (CrashLoopBackOff, ImagePullBackOff, Pending)
- Troubleshooting nodes (NotReady, DiskPressure, MemoryPressure)
- Troubleshooting networking y DNS
- **Conexión con Zensy:** los hallazgos H-01 a H-05 son laboratorio real de troubleshooting — documentar el análisis y resolución en `labs/05-kubernetes-cka/`

#### Semana 31-34: Simulacros y práctica intensiva

- killer.sh (incluido con el voucher del examen) — al menos 3 simulacros completos
- Cronómetro: el examen dura 2h, hay que practicar velocidad con `kubectl`
- Alias y shortcuts imprescindibles:
  ```bash
  alias k=kubectl
  export do="--dry-run=client -o yaml"
  export now="--force --grace-period 0"
  ```
- Revisar `certifications/cka.md` — checklist completo

#### Semana 35: Examen CKA

- **Examen CKA**
- Si hay reintento disponible: siguiente semana
- Actualizar LinkedIn, `PROGRESS.md`, publicar apuntes en `modules/05-kubernetes-cka.md`

#### Vault Associate (mes 9 — inmediatamente después de CKA)

**Costo:** ~$70-95  
**Horas estimadas:** 20-30h (bajo esfuerzo — ya operás Vault con KMS en producción)

- Vault architecture: dev mode vs production, seals, unseal
- Auth methods: AWS, Kubernetes, AppRole, Token
- Secret engines: KV v2, PKI, Database, AWS
- Policies: HCL, capabilities
- Laboratorio: Vault + External Secrets Operator (tu setup real en Zensy como referencia)
- **Examen Vault Associate**

**Entregables al cierre de Fase 3:**
- [x] Certificado CKA
- [x] Certificado Vault Associate
- [x] Módulos `05-kubernetes-cka.md` y `10-security-vault-cks.md` (sección Vault)
- [x] Labs documentados en `labs/05-kubernetes-cka/`
- [x] Análisis de H-01 a H-05 publicado como caso de troubleshooting real

---

### Fase 4 — AWS Solutions Architect Associate (meses 10-12)

**Certificación:** AWS Certified Solutions Architect – Associate (SAA-C03)  
**Costo:** ~$150  
**Horas estimadas:** 80-100h

**Ventaja de tu perfil:** operás en producción EKS, RDS, Transit Gateway, Route53, ECR, ALB, IAM, SSO. La brecha está en servicios que no usás directamente (SQS, SNS, SageMaker, etc.) y en conocer la profundidad del examen (arquitectura, not-managed vs managed, costos, disaster recovery).

#### Dominios del examen (pesos SAA-C03)

| Dominio | Peso |
|---------|------|
| Design Secure Architectures | 30% |
| Design Resilient Architectures | 26% |
| Design High-Performing Architectures | 24% |
| Design Cost-Optimized Architectures | 20% |

#### Semana 36-39: Core services

- IAM: usuarios, roles, policies, SCP, permission boundaries
- VPC: subnets, route tables, Internet Gateway, NAT, VPC Peering, Transit Gateway, PrivateLink
- EC2: tipos, pricing models (On-Demand, Reserved, Spot, Savings Plans), Auto Scaling, Launch Templates
- S3: storage classes, lifecycle policies, versioning, replication, encryption, pre-signed URLs
- RDS: Multi-AZ, Read Replicas, Aurora, backup, encryption
- EKS, ECS, Lambda: cuándo usar cada uno (architectural decision)

#### Semana 40-43: Servicios avanzados + patrones

- CloudFront, Route53 (políticas de routing: weighted, latency, failover, geolocation)
- ALB, NLB, GLB: cuándo usar cada uno
- SQS, SNS, EventBridge: arquitecturas event-driven
- ElastiCache, DynamoDB: cuándo preferir sobre RDS
- CloudWatch, X-Ray, CloudTrail: observabilidad y auditoría
- KMS, Secrets Manager, Parameter Store: gestión de secretos (tu contexto Vault)
- Disaster Recovery: RTO/RPO, backup/restore, pilot light, warm standby, multi-region active-active

#### Semana 44-46: Simulacros y áreas débiles

- Tutorialsdojo o Stephane Maarek practice exams (los mejores para SAA)
- Identificar servicios menos familiares y reforzar
- Revisar `certifications/aws-saa.md`

#### Semana 47-48: Examen

- Simulacro final completo
- **Examen AWS SAA-C03**
- Actualizar LinkedIn, `PROGRESS.md`, `CHANGELOG.md`

**Entregables al cierre de Fase 4:**
- [x] Certificado AWS Solutions Architect Associate
- [x] Módulo `08-aws-saa.md` completo
- [x] CV y LinkedIn reflejando todas las certificaciones obtenidas
- [x] Programa completo v1.0 publicado y mantenido

---

## Template semanal de seguimiento

Copiar en `PROGRESS.md` al cierre de cada semana:

```markdown
## Semana XX — [fecha inicio] al [fecha fin]

**Fase actual:** [nombre de la fase]
**Certificación en curso:** [nombre]

### Horas de estudio
- Objetivo: Xh
- Real: Xh

### Objetivos de la semana
- [ ] Objetivo 1
- [ ] Objetivo 2

### Laboratorios realizados
- Lab X: [descripción breve]

### Problemas encontrados
- [Problema] → [Solución / pendiente]

### Lecciones aprendidas
- 

### Estado general
[ ] En tiempo  [ ] Adelantado  [ ] Atrasado — motivo: ___
```

---

## Presupuesto total

| Certificación | Costo USD |
|---------------|-----------|
| Codefresh GitOps Fundamentals | Gratis |
| Oracle OCI Foundations | Gratis |
| Terraform Associate | ~$70 |
| CKA (incluye reintento) | ~$445 |
| Vault Associate | ~$70-95 |
| AWS Solutions Architect Associate | ~$150 |
| **Total** | **~$735-760** |

> Tip: revisar si Zensy cubre vouchers de certificación (algunos employers lo hacen como parte de desarrollo profesional). También AWS re:Invent y KubeCon frecuentemente distribuyen vouchers.

---

## KPIs del programa

Al finalizar los 12 meses:

| KPI | Objetivo |
|-----|---------|
| Certificaciones obtenidas | ≥ 5 de 6 planificadas |
| Horas de estudio totales | ≥ 400h |
| Laboratorios completados | ≥ 30 |
| Proyectos públicos en GitHub | ≥ 1 completo y documentado |
| Posición LinkedIn actualizada | ✅ |
| Semanas con registro en PROGRESS.md | ≥ 45 de 48 |
