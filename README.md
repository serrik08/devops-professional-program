# 📘 DevOps Engineer Professional Program

> Programa de formación profesional de 12 meses para consolidar un perfil de **DevOps Senior / Platform Engineer / SRE** competitivo a nivel internacional.

---

## Autor

**Sergio Ricardo Gerónimo Rocha**  
DevOps / Infrastructure Engineer  
Cochabamba, Bolivia  
Experiencia en desarrollo de software: desde enero 2017 (~9 años)  
Experiencia en DevOps: en curso (transición activa)

---

## Stack tecnológico actual

AWS · EKS (Kubernetes 1.35, arm64) · ArgoCD · Terraform · Vault · Istio · Crossplane · Karpenter · External Secrets · VictoriaMetrics · Loki · ClickHouse · Argo Rollouts · Velero · BunkerWeb · GitHub Actions

---

## Objetivo del programa

Construir en 12 meses un perfil técnico verificable y diferenciado, combinando:

- **Certificaciones de peso real** (no cursos sueltos)
- **Evidencia pública** derivada de trabajo real en producción
- **Documentación profesional** de cada etapa de aprendizaje

---

## Certificaciones objetivo

| # | Certificación | Costo | Mes objetivo |
|---|---------------|-------|-------------|
| 1 | Codefresh GitOps Fundamentals | Gratis | 1-2 |
| 2 | Oracle OCI Foundations | Gratis | 1-2 |
| 3 | HashiCorp Terraform Associate | ~$70 | 3-5 |
| 4 | CKA — Certified Kubernetes Administrator | ~$445 | 6-9 |
| 5 | HashiCorp Vault Associate | ~$70-95 | 9 |
| 6 | AWS Solutions Architect Associate | ~$150 | 10-12 |

**Inversión total estimada:** ~$735-760 USD en 12 meses

---

## Estructura del repositorio

```
devops-professional-program/
│
├── README.md              ← Este archivo
├── ROADMAP.md             ← Planificación anual y semanal
├── PROGRESS.md            ← Seguimiento de avance (actualización semanal)
├── CHANGELOG.md           ← Versiones y actualizaciones del programa
│
├── modules/               ← Un archivo por módulo temático
│   ├── 00-foundations.md
│   ├── 01-linux.md
│   ├── 02-networking.md
│   ├── 03-git-advanced.md
│   ├── 04-docker.md
│   ├── 05-kubernetes-cka.md
│   ├── 06-terraform.md
│   ├── 07-gitops-argocd.md
│   ├── 08-aws-saa.md
│   ├── 09-observability.md
│   ├── 10-security-vault-cks.md
│   ├── 11-cicd.md
│   └── 12-platform-engineering.md
│
├── certifications/        ← Guía específica por examen
│   ├── codefresh-gitops.md
│   ├── oci-foundations.md
│   ├── terraform-associate.md
│   ├── cka.md
│   ├── vault-associate.md
│   └── aws-saa.md
│
├── labs/                  ← Laboratorios prácticos por módulo
│   └── (un directorio por módulo)
│
├── projects/              ← Proyectos públicos del portafolio
│   ├── 01-migration-runbook/
│   └── (proyectos adicionales)
│
├── diagrams/              ← Diagramas de arquitectura (draw.io, Mermaid)
│
├── scripts/               ← Scripts reutilizables creados durante el programa
│
├── templates/             ← Plantillas de documentos, CVs, etc.
│
└── notes/                 ← Apuntes libres por tema
```

---

## Metodología

**Learn → Build → Document → Share**

Por cada hora de teoría: mínimo 2 horas de práctica con laboratorios reales.

Los laboratorios están diseñados para ejecutarse sobre infraestructura real (AWS, EKS, etc.) siempre que sea posible, no solo sobre entornos simulados.

---

## Filosofía del programa

> Las certificaciones validan lo que ya sabés.  
> Los proyectos públicos demuestran cómo trabajás.  
> La documentación diferencia a los seniors de los demás.

Este programa asume que la experiencia práctica ya existe. El objetivo no es "aprender desde cero" sino **formalizar, profundizar y hacer visible** lo que ya se hace en producción.

---

## Versión

`v1.0` — Inicio del programa  
Última actualización: 2026-06
