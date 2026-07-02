# Module 07: GitOps & Argo CD

This module contains technical study notes, architectural concepts, and practical commands related to GitOps principles and the Argo CD ecosystem.

**Primary Learning Path:** `learning-paths/gitops/`
**Current Focus:** Akuity Academy - Introduction to CD and GitOps with Argo CD

---

## 1. GitOps Core Principles

> **Note:** Add your notes here after watching the initial Akuity lessons.
> - What makes GitOps different from traditional CI/CD?
> - The 4 Principles of GitOps (Declarative, Versioned, Pulled Automatically, Continuously Reconciled).

---

## 2. Argo CD Architecture

> **Note:** Document how Argo CD components interact.
> - `argocd-server`: API/UI component
> - `argocd-repo-server`: Clones and caches Git repositories
> - `argocd-application-controller`: The reconciliation loop

---

## 3. Core CRDs (Custom Resource Definitions)

### Application

An `Application` connects a Git repository (source) to a Kubernetes cluster (destination).

```yaml
# Example: Basic Application CRD
apiVersion: argoproj.io/v1alpha1
kind: Application
metadata:
  name: my-app
  namespace: argocd
spec:
  project: default
  source:
    repoURL: 'https://github.com/my-org/my-repo.git'
    path: k8s/overlays/dev
    targetRevision: HEAD
  destination:
    server: 'https://kubernetes.default.svc'
    namespace: my-app-dev
  syncPolicy:
    automated:
      prune: true
      selfHeal: true
```

### ApplicationSet / Project

> **Note:** Add notes here about AppSets (generators, templates) and AppProjects (RBAC, source/destination restrictions).

---

## 4. Synchronization & Health

### Sync Phases and Waves
> **Note:** How does Argo CD decide what order to apply resources in? Document Sync Waves.

### Health Assessment
> **Note:** How does Argo CD know a Deployment or Custom Resource is actually "Healthy"?

---

## 5. Helpful Commands (`argocd` CLI)

```bash
# Login to ArgoCD server
argocd login <server>

# List all applications
argocd app list

# Sync an application manually
argocd app sync <app-name>
```

---

## 6. Troubleshooting (Production Scenarios)

*Document real-world issues encountered in `plat-dev` or `plat-staging` here.*

- **Scenario 1:** OutOfSync loop due to mutating webhooks.
  - *Symptom:* ...
  - *Fix:* Ignore differences in `Application` spec.
