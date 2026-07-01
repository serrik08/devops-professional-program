# DevOps Engineer Professional Program

> A professional self-paced program to become a Senior DevOps / Platform Engineer through real-world projects, industry-recognized certifications, and production-grade labs.

![Status](https://img.shields.io/badge/status-in%20progress-blue)
![Version](https://img.shields.io/badge/version-1.1-informational)
![License](https://img.shields.io/badge/license-MIT-green)
![Kubernetes](https://img.shields.io/badge/Kubernetes-1.35-326CE5?logo=kubernetes&logoColor=white)
![Terraform](https://img.shields.io/badge/Terraform-Associate-7B42BC?logo=terraform&logoColor=white)
![AWS](https://img.shields.io/badge/AWS-SAA-FF9900?logo=amazonaws&logoColor=white)
![ArgoCD](https://img.shields.io/badge/ArgoCD-GitOps-EF7B4D?logo=argo&logoColor=white)

---

This repository documents my professional development journey while transitioning from Software Engineering (~9 years) to DevOps and Platform Engineering.

Unlike traditional study notes, this repository focuses on:

- **Production-oriented labs** — built on real infrastructure (AWS EKS, Vault, ArgoCD, Terraform)
- **Public portfolio projects** — documented with architecture diagrams and runbooks
- **Certification preparation** — 6 industry-recognized certifications over 12 months
- **Engineering best practices** — ADRs, cheatsheets, and professional documentation

---

## Current Status

| | |
|---|---|
| **Program Version** | v1.0 |
| **Start Date** | July 2026 |
| **Target Completion** | July 2027 |
| **Current Phase** | Phase 0 — Setup |
| **Current Module** | Module 00 — Foundations |
| **Next Certification** | Akuity GitOps / ArgoCD |

**Overall Progress**

```
Phase 1 — Free certs      ░░░░░░░░░░  0%
Phase 2 — Terraform       ░░░░░░░░░░  0%
Phase 3 — CKA + Vault     ░░░░░░░░░░  0%
Phase 4 — AWS SAA         ░░░░░░░░░░  0%
```

---

## Why this repository?

Many roadmaps stop at theory.

This one is different.

Everything learned here must eventually become one of the following:

- a lab with real infrastructure
- a public portfolio project
- technical documentation
- a cheatsheet or runbook
- automation

Learning without building is incomplete.

---

## Program Goals

- [ ] 6 industry-recognized certifications
- [ ] 1 public portfolio project (EKS migration runbook)
- [ ] 30+ Kubernetes labs (CKA-focused)
- [ ] 20+ Terraform labs
- [ ] 3 custom skills for OpenCode agent
- [ ] kubectl, terraform, helm, aws cheatsheets

---

## Learning Philosophy

```
Learn
  ↓
Practice
  ↓
Build
  ↓
Document
  ↓
Teach
  ↓
Repeat
```

---

## Learning Paths

Instead of building a repository of certifications, this is a repository of **competencies**. If a certification disappears tomorrow, the competency remains.

- **GitOps** (ArgoCD, Akuity, Flux, Kargo)
- **Terraform** (IaC, State Management, Modules, AWS Provider)
- **Kubernetes** (CKA, Cluster Administration, Troubleshooting)
- **AWS** (Architecture, Networking, Compute, Storage)
- **Security** (Vault, CKS concepts, IAM)

Each path contains:
`courses.md` | `labs.md` | `certifications.md` | `resources.md` | `notes.md` | `project.md`

---

## Repository Structure

```
devops-professional-program/

    README.md              - This file
    ROADMAP.md             - 12-month plan with weekly breakdown
    CHANGELOG.md           - Program versions and updates
    AGENTS.md              - OpenCode agent instructions

    learning-paths/        - Competency-based hubs
        aws/
        gitops/
        kubernetes/
        security/
        terraform/

    career/                - Career development and evaluations
        certification-evaluation-framework.md
        certification-matrix.md

    modules/               - Granular technical topics
        00-foundations/
        01-linux/
        02-networking/
        03-git-advanced/
        04-docker/
        05-kubernetes-cka/
        06-terraform/
        07-gitops-argocd/
        08-aws-saa/
        09-observability/
        10-security-vault-cks/
        11-cicd/
        12-platform-engineering/

    books/                 - Book summaries and notes
    cheatsheets/           - Quick reference cards
    adr/                   - Architecture Decision Records
    resources/             - General links and shared materials
    weekly/                - Weekly progress logs and reflections
    diagrams/              - Architecture diagrams (Mermaid, draw.io)
    scripts/               - Reusable automation scripts
```

---

## Current Stack (Production Context)

All labs are designed around this real-world stack:

| Layer | Technology |
|-------|-----------|
| Cloud | AWS (EKS, RDS, ALB, Route53, ECR, TGW, IAM, KMS, SSO) |
| Orchestration | Kubernetes 1.35 arm64, Karpenter, Istio 1.25 mTLS |
| GitOps | ArgoCD v2.14, Argo Rollouts, Helm, Kustomize |
| IaC | Terraform (multi-workspace, remote state S3) |
| Secrets | Vault 0.29.1 + KMS, External Secrets 0.14.4 |
| Observability | VictoriaMetrics, Loki, Grafana |
| Platform | Crossplane 1.19, Restate, PeerDB, ClickHouse |
| Security | Istio mTLS, BunkerWeb WAF, RBAC, OPA |
| CI/CD | GitHub Actions, ArgoCD |

---

## Author

**Sergio Ricardo Gerónimo Rocha**
DevOps / Infrastructure Engineer — Cochabamba, Bolivia
Software engineering experience: since January 2017 (~9 years)
DevOps transition: active

---

## License

MIT
