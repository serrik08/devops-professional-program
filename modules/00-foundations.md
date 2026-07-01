# Módulo 00 — Foundations

> Diagnóstico inicial, análisis de brechas y objetivos del programa.

---

## Objetivos del módulo

- Definir el perfil inicial con honestidad técnica
- Identificar fortalezas que ya existen y no necesitan construirse desde cero
- Identificar brechas reales (no percibidas) entre el perfil actual y el perfil objetivo
- Establecer el perfil de salida del programa

---

## Perfil inicial (julio 2026)

### Experiencia general
- **Desarrollo de software:** desde enero 2017 (~9 años)
- **Rol DevOps:** en curso — transición activa desde desarrollo
- **Idiomas:** español (nativo), inglés técnico (lectura de docs — nivel B1-B2)

### Stack actual en producción (Zensy)

| Área | Tecnología | Nivel |
|------|-----------|-------|
| Cloud | AWS (EKS, RDS, ALB, Route53, ECR, TGW, IAM, KMS, SSO) | Avanzado |
| Contenedores | Docker, EKS 1.35 arm64 | Avanzado |
| Orquestación | Kubernetes (EKS, Karpenter, Istio, Envoy) | Intermedio-Avanzado |
| GitOps | ArgoCD v2.14, Argo Rollouts, ApplicationSets, Helm, Kustomize | Avanzado |
| IaC | Terraform (módulos, workspaces, remote state en S3) | Intermedio |
| Secrets | Vault 0.29.1 + KMS, External Secrets Operator 0.14.4 | Intermedio |
| Observabilidad | VictoriaMetrics, Loki, Grafana | Básico-Intermedio |
| Service Mesh | Istio 1.25 mTLS strict, BunkerWeb WAF | Intermedio |
| Plataforma | Crossplane 1.19, Restate, PeerDB, ClickHouse Operator | Intermedio |
| CI/CD | GitHub Actions, ArgoCD, pipelines en cuenta `auto` | Intermedio |
| Seguridad | OWASP, diplomado en ciberseguridad (792h), RBAC K8s | Básico-Intermedio |
| Linux | WSL Ubuntu, administración de servidores | Intermedio |
| Networking | TCP/IP, DNS, VPC, TGW, Route53, ALB/NLB | Intermedio |
| Bases de datos | PostgreSQL 17, ClickHouse 24.8, Oracle PL/SQL | Intermedio |
| Backend | Python, Node.js, C#, .NET | Intermedio (contexto dev anterior) |

### Certificaciones previas relevantes
- Diplomado en Ciberseguridad y Auditoría Informática (792h)
- Cisco CCNA Fundamentos de Networking
- OWASP TOP 10 (Udemy)

---

## Perfil objetivo (julio 2027)

Un ingeniero que pueda postular y ser contratado para roles de:

- **DevOps Engineer (Senior)** en empresas con stack cloud-native
- **Platform Engineer** en equipos con GitOps, Kubernetes y IaC
- **SRE** en empresas internacionales (Latam, US, Europa remoto)

Con capacidad de demostrar competencia mediante:
1. Certificaciones verificables por terceros (no solo cursos completados)
2. Evidencia pública en GitHub (proyectos documentados, no solo código)
3. Historial de resolución de problemas reales en producción

---

## Análisis de brechas (GAP Analysis)

### Fortalezas reales — no necesitan construirse

- Kubernetes en producción (EKS, arm64, Karpenter, Istio, Argo)
- AWS multi-account con IAM Identity Center/SSO
- GitOps con ArgoCD y múltiples entornos (dev, staging, prod)
- Vault + External Secrets en producción
- Terraform con remote state y múltiples workspaces
- Experiencia en migración compleja de infraestructura (12 cuentas AWS)
- Background en desarrollo de software (~9 años) — entiende el contexto de los servicios que despliega
- Background en ciberseguridad (diplomado 792h) — diferenciador para CKS y roles de seguridad

### Brechas identificadas

| Área | Brecha específica | Módulo que la cubre |
|------|------------------|---------------------|
| Kubernetes | Administración de cluster "vanilla" (`kubeadm`), no solo EKS managed | 05-kubernetes-cka |
| Kubernetes | ETCD backup/restore, upgrade de control plane | 05-kubernetes-cka |
| Kubernetes | NetworkPolicies avanzadas, CNI profundo | 05-kubernetes-cka |
| Terraform | Testing (Terratest, `terraform test`), Sentinel | 06-terraform |
| AWS | Servicios que no usa en Zensy: SQS, SNS, EventBridge, SageMaker, Step Functions | 08-aws-saa |
| AWS | Architectural decision frameworks (cuándo usar qué servicio y por qué) | 08-aws-saa |
| AWS | Costos: Savings Plans, Reserved vs Spot decision patterns | 08-aws-saa |
| Observabilidad | OpenTelemetry, Tempo (tracing), AlertManager avanzado | 09-observability |
| Linux | Nivel de administración profundo para LFCS (systemd, performance tuning) | 01-linux |
| CI/CD | GitHub Actions avanzado (matrices, reusable workflows, OIDC con AWS) | 11-cicd |
| Certificaciones | Ninguna certificación de plataforma reconocida internacionalmente aún | Todo el programa |
| Evidencia pública | Sin repositorios públicos de referencia todavía | projects/ |
| Inglés | B1-B2 técnico (lectura OK, escritura y conversación en desarrollo) | transversal |

---

## Objetivos SMART del programa

### Objetivo 1 — Certificaciones
**Específico:** Obtener 5 de las 6 certificaciones planificadas (Codefresh, OCI, Terraform, CKA, Vault, AWS SAA)  
**Medible:** Certificados verificables en LinkedIn y en `certifications/` del repo  
**Alcanzable:** Sí — perfil actual permite reducir tiempo de estudio significativamente vs. un perfil junior  
**Relevante:** Son las certificaciones con mayor frecuencia en requisitos de vacantes DevOps/SRE internacionales  
**Temporal:** Antes de julio 2027

### Objetivo 2 — Evidencia pública
**Específico:** Al menos 1 proyecto público en GitHub completamente documentado (arquitectura, diagramas, README profesional)  
**Medible:** Repo accesible, con README, diagrams/ y documentación de decisiones de diseño  
**Alcanzable:** Sí — se basa en trabajo real de Zensy sanitizado, no en proyectos desde cero  
**Relevante:** Un proyecto público bien documentado pesa más que 10 certificaciones de cursos  
**Temporal:** Antes del mes 6

### Objetivo 3 — Posición laboral
**Específico:** Estar en condiciones de postular (o recibir inbound) a roles DevOps Senior / Platform Engineer con compensación superior a la actual  
**Medible:** Al menos 3 procesos de selección iniciados en el Q4 2027 con feedback técnico positivo  
**Alcanzable:** Con CKA + Terraform + AWS SAA como base mínima, sí  
**Relevante:** Es el objetivo final del programa  
**Temporal:** Antes de diciembre 2027

---

## Organización del tiempo de estudio

### Horas disponibles (estimado realista)
- Días de semana: 1-1.5h/día (después del trabajo en Zensy)
- Fin de semana: 3-4h (distribuidas entre sábado y domingo)
- **Total semanal: 8-10h** (objetivo mínimo sostenible)

> Durante fases de migración activa en Zensy (resolución de H-01 a H-05, promoción a staging), reducir a 5-6h/semana es válido — el programa no es más importante que el trabajo. Ajustar en `PROGRESS.md`.

### Estructura sugerida por día de semana
- **Lunes:** teoría / lectura de documentación oficial
- **Martes-Miércoles:** práctica / laboratorios
- **Jueves:** revisión + apuntes en el módulo correspondiente
- **Viernes:** checklist semanal + actualizar `PROGRESS.md`
- **Sábado-Domingo:** laboratorio más extenso o simulacro de examen

---

## Herramientas del programa

| Herramienta | Uso |
|-------------|-----|
| GitHub | Repositorio del programa, proyectos públicos |
| Obsidian o VS Code | Edición de Markdown local |
| Multipass / Vagrant | VMs locales para laboratorios de `kubeadm` (CKA) |
| Oracle Free Tier | Laboratorios de OCI sin costo |
| AWS `plat-dev` | Laboratorios reales en EKS (cuando el acceso lo permita) |
| killer.sh | Simulacros CKA (incluido en el voucher del examen) |
| Tutorialsdojo | Simulacros AWS SAA |

---

## Checklist de finalización del módulo 00

- [ ] Perfil inicial documentado con honestidad (sin inflar ni minimizar)
- [ ] GAP analysis completo revisado
- [ ] Objetivos SMART escritos y firmados (comprometerse con ellos)
- [ ] Horario de estudio definido y bloqueado en calendario
- [ ] Repositorio `devops-professional-program` creado en GitHub
- [ ] `PROGRESS.md` configurado con template semanal
- [ ] LinkedIn actualizado con experiencia actual y stack real
- [ ] Herramientas instaladas (Multipass o Vagrant para labs de CKA)
