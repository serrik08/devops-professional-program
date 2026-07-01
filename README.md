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
| **Next Certification** | Codefresh GitOps Fundamentals |

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

## Certifications Roadmap

| # | Certification | Cost | Target | Status |
|---|---------------|------|--------|:------:|
| 1 | Codefresh GitOps Fundamentals | Free | Month 2 | ⏳ |
| 2 | Oracle OCI Foundations | Free | Month 2 | ⏳ |
| 3 | HashiCorp Terraform Associate | ~$70 | Month 5 | ⏳ |
| 4 | CKA — Certified Kubernetes Administrator | ~$445 | Month 9 | ⏳ |
| 5 | HashiCorp Vault Associate | ~$70-95 | Month 9 | ⏳ |
| 6 | AWS Solutions Architect Associate | ~$150 | Month 12 | ⏳ |

**Estimated total investment:** ~$735-760 USD

---

## Repository Structure

```
devops-professional-program/

    README.md              - This file
    ROADMAP.md             - 12-month plan with weekly breakdown
    PROGRESS.md            - Weekly tracking log
    CHANGELOG.md           - Program versions and updates
    AGENTS.md              - OpenCode agent instructions

    modules/               - One file (or folder) per topic
        00-foundations.md
        01-linux.md
        02-networking.md
        03-git-advanced.md
        04-docker.md
        05-kubernetes/     - Expanded structure (CKA)
        06-terraform.md
        07-gitops-argocd.md
        08-aws-saa.md
        09-observability.md
        10-security-vault-cks.md
        11-cicd.md
        12-platform-engineering.md

    certifications/        - Exam-specific guides
    labs/                  - Hands-on labs by module
    projects/              - Public portfolio projects
    cheatsheets/           - Quick reference cards
    adr/                   - Architecture Decision Records
    diagrams/              - Architecture diagrams (Mermaid, draw.io)
    scripts/               - Reusable automation scripts
    notes/                 - Free-form notes by topic
    templates/             - Document templates
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
