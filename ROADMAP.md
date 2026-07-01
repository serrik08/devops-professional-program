# 🗺️ ROADMAP — DevOps Engineer Professional Program

> Version: 1.1 | Duration: 12 months | Start: July 2026

---

## Program Principles

1. **Strong certifications over many** — 6 strategic certifications are worth more than 90 random courses.
2. **Real evidence over invented projects** — Documenting sanitized production work (runbooks, architecture) is more valuable than tutorial exercises.
3. **Sustainable over ambitious** — The plan is calibrated for a full-time engineer with an active migration project and freelance consulting on the side.
4. **Competency-based, not just cert-based** — Certifications validate what you already know. The focus is on the `learning-paths/` hubs.

---

## Annual Overview

```text
Month  01-02  │ Free Foundation: GitOps (Akuity) + OCI Foundations + Public Profile
Month  03-05  │ Terraform Associate + First Public Project
Month  06-09  │ CKA (Main block) + Vault Associate
Month  10-12  │ AWS Solutions Architect Associate
```

---

## Phase Details

### Phase 0 — Setup (Weeks 1-2)

**Objective:** Prepare the infrastructure of the program before studying.

- [x] Create GitHub repository `devops-professional-program`.
- [x] Configure folder structure (Competency-based).
- [x] Create `weekly/` structure for scalable progress tracking.
- [x] Update LinkedIn (headline, current experience, skills).
- [x] Identify available study hours (Target: 6-8h/week).

---

### Phase 1 — Free Foundation (Months 1-2)

**Competencies:** GitOps (ArgoCD) & Oracle Cloud Infrastructure (OCI)
**Cost:** $0  
**Estimated hours:** 30-40h

#### Week 1-2: GitOps & ArgoCD (Akuity Academy)

Instead of starting with OCI, we start with GitOps because it provides an immediate return on investment for daily production work.

- **Activity:** Akuity Academy – Introduction to CD and GitOps with Argo CD.
- **Focus:** GitOps principles, Application CRDs, Sync strategies, Helm deployments.
- **Lab:** Map the course concepts to the real setup in `argocd-deploy-non-prod`. Update `learning-paths/gitops/labs.md`.

#### Week 3-4: GitOps Advanced & Projects

- **Activity:** Akuity Academy – Promote Applications Across Environments with Kargo.
- **Focus:** Progressive delivery, multi-environment promotions.
- **Deliverable:** Populate `learning-paths/gitops/` with notes, official documentation links, and the project architecture.

#### Week 5-6: Oracle OCI Foundations

- **Activity:** OCI Architecture, IAM, Compute, Networking, Storage, Databases, Security.
- **Lab:** Oracle Free Tier environment setup.

#### Week 7-8: OCI Foundations — Exam & Phase Closure

- **Activity:** Exam preparation and mock tests.
- **Exam:** OCI Foundations.
- **Project:** Start `projects/01-migration-runbook/` base structure.

**Deliverables for Phase 1:**
- [ ] Akuity Academy completed and documented in `learning-paths/gitops/`.
- [ ] OCI Foundations Certified.
- [ ] LinkedIn updated.

---

### Phase 2 — Terraform Associate (Months 3-5)

**Certification:** HashiCorp Terraform Associate 003  
**Cost:** ~$70  
**Estimated hours:** 60-80h

*Advantage:* Terraform + AWS is already used in production (`plat-dev`, `plat-staging`). Study time is reduced.

#### Week 9-10: Foundations Review
- HCL syntax, data types, variables, outputs.
- Providers, resources, data sources.
- State: local vs remote (S3 + DynamoDB).
- Modules: structure, reuse.

#### Week 11-12: Intermediate
- Workspaces, `terraform import`, `moved` blocks.
- `terraform state` manipulation.
- Testing in CI/CD (`terraform validate`, `terraform plan`).
- Backends, locking.

#### Week 13-15: Lab + Public Project
- **Lab:** Deploy real infra in `plat-dev` using a custom module.
- **Public Project:** `projects/01-migration-runbook/` — Sanitized migration runbook documenting Terraform patterns used in production.

#### Week 16-18: Exam Prep & Execution
- Official HashiCorp mock exams.
- **Exam:** Terraform Associate.

---

### Phase 3 — CKA (Months 6-9)

**Certification:** Certified Kubernetes Administrator (CNCF)  
**Cost:** ~$445 (includes one retake)  
**Estimated hours:** 120-150h

*Advantage:* Operating EKS 1.35 arm64 with Karpenter, Istio, ArgoCD in production. The gap is in "vanilla" cluster administration (`kubeadm`).

#### Domains
- Troubleshooting: 30%
- Cluster Architecture, Install & Config: 25%
- Services & Networking: 20%
- Workloads & Scheduling: 15%
- Storage: 10%

#### Schedule
- **Week 19-22:** `kubeadm`, ETCD, Control Plane components, RBAC. Lab: Local VMs.
- **Week 23-26:** Deployments, Probes, Limits, Services, Ingress, NetworkPolicies, CoreDNS, CNI.
- **Week 27-30:** Storage (PV, PVC, SC), Troubleshooting. *Connect with production findings (H-01 to H-05).*
- **Week 31-34:** `killer.sh` mock exams. Speed practice.
- **Week 35:** **CKA Exam.**

#### Vault Associate (Month 9 — Immediately after CKA)
- **Cost:** ~$70-95 | **Hours:** 20-30h
- Architecture, Auth methods, Secret engines, Policies.
- **Lab:** Vault + External Secrets Operator.
- **Exam:** Vault Associate.

---

### Phase 4 — AWS Solutions Architect Associate (Months 10-12)

**Certification:** AWS Certified Solutions Architect – Associate (SAA-C03)  
**Cost:** ~$150  
**Estimated hours:** 80-100h

*Advantage:* Operating EKS, RDS, TGW, Route53, ECR, ALB, IAM, SSO in production. The gap is in unmanaged vs managed tradeoffs and unused services (SQS, SNS).

#### Schedule
- **Week 36-39:** Core Services (IAM, VPC, EC2, S3, RDS, Compute tradeoffs).
- **Week 40-43:** Advanced Services & Patterns (CloudFront, Route53, LBs, Event-driven, Caching, Disaster Recovery).
- **Week 44-46:** TutorialsDojo mock exams.
- **Week 47-48:** **AWS SAA-C03 Exam.**

---

## Weekly Tracking

See `weekly/README.md` and individual weekly logs.

## Total Budget

| Item | Estimated Cost |
|------|----------------|
| Akuity GitOps / OCI | Free |
| Terraform Associate | ~$70 |
| CKA (includes retake) | ~$445 |
| Vault Associate | ~$70-95 |
| AWS SAA | ~$150 |
| **Total** | **~$735-760** |

---

## Program KPIs

By the end of Month 12:

| KPI | Target |
|-----|--------|
| Certifications/Paths | ≥ 5 of 6 planned |
| Total Study Hours | ≥ 400h |
| Completed Labs | ≥ 30 |
| Public Projects | ≥ 1 fully documented |
| LinkedIn Updated | ✅ |
| Weekly Logs | ≥ 45 of 48 weeks tracked in `weekly/` |
