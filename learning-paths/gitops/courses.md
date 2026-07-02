# GitOps Courses

This document tracks the formal courses, tutorials, and structured learning material for the GitOps competency.

---

## 1. Introduction to CD and GitOps with Argo CD

- **Platform:** [Akuity Academy](https://akuity.io/academy/course/intro-to-argo-cd)
- **Status:** 🔄 In Progress
- **Cost:** Free
- **Duration:** ~2 hours (23 lessons)
- **Instructor / Creator:** Akuity (Founders of Argo CD)
- **Priority:** High / Foundational

### Why this course?
It provides the most authoritative explanation of Argo CD internals, straight from the creators. It aligns perfectly with daily operations on the `plat-dev` / `plat-staging` environments.

### Course Outline & Tracking
- [ ] 01. What is GitOps?
- [ ] 02. What is Argo CD?
- [ ] 03. Argo CD Architecture
- [ ] 04. Core Concepts: Applications
- [ ] 05. Core Concepts: Application Health & Status
- [ ] 06. Core Concepts: Synchronization
- [ ] 07. Deploying with Helm & Kustomize
- [ ] 08. Hands-on Labs (See `modules/07-gitops-argocd/labs/`)

---

## 2. Promote Applications Across Environments with Kargo

- **Platform:** [Akuity Academy](https://akuity.io/academy/course/promote-apps-across-envs-with-kargo)
- **Status:** ⏳ Pending
- **Cost:** Free
- **Duration:** ~2 hours
- **Instructor / Creator:** Akuity
- **Priority:** Medium (Post-ArgoCD Mastery)

### Why this course?
Argo CD handles deployment, but Kargo handles *promotion* across stages (e.g., Dev → Staging → Prod). This is a critical next step for building mature Platform Engineering pipelines without writing brittle CI scripts.

### Course Outline & Tracking
- [ ] 01. Introduction to Kargo
- [ ] 02. Kargo Architecture & CRDs (Stages, Promotions)
- [ ] 03. Integrating Kargo with Argo CD
- [ ] 04. Multi-environment promotion labs

---

## 3. Codefresh GitOps Fundamentals (Optional/Archived)

- **Platform:** Codefresh Academy
- **Status:** ⏸️ Paused (Deprioritized in favor of Akuity)
- **Cost:** Free
- **Notes:** While a valid certification, Akuity provides more direct alignment with the current Argo CD stack used in production. This will only be pursued if the formal certification badge is strictly required later.

