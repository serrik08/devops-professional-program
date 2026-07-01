# AGENTS.md — DevOps Professional Program

## Project context

This repository is a 12-month professional training program to build a Senior DevOps / Platform Engineer profile. It is not a code project — it is structured technical documentation in Markdown.

**Author:** Sergio Ricardo Gerónimo Rocha
**Current stack:** AWS EKS 1.35 arm64 · ArgoCD v2.14 · Terraform · Vault 0.29.1 · Istio 1.25 · Karpenter · External Secrets · Crossplane · VictoriaMetrics · Loki

## Language

**All content is written in English.** No exceptions for public files.
Personal notes in `notes/` may be written in Spanish.

## File placement rules

| Content type | Location |
|-------------|----------|
| Module study notes | `modules/<NN>-<name>.md` or `modules/<NN>-<name>/README.md` |
| Certification guides | `certifications/<name>.md` |
| Hands-on labs | `labs/<module-name>/<lab-name>.md` |
| Portfolio projects | `projects/<NN>-<name>/` |
| Quick reference | `cheatsheets/<tool>.md` |
| Architecture decisions | `adr/<NNNN>-<title>.md` |
| Architecture diagrams | `diagrams/` |
| Reusable scripts | `scripts/` |
| Free-form notes | `notes/` |

Never create files outside these locations without explicit confirmation.

## Module structure rules

Small modules (Git, Docker, Linux): single `.md` file in `modules/`

Large modules (Kubernetes, Terraform, AWS): expanded folder structure:
```
modules/05-kubernetes/
    README.md          - main module content
    labs/              - lab files
    cheatsheets/       - kubectl, helm quick refs
    manifests/         - example YAML files
    notes/             - free-form notes
```

Only `05-kubernetes/`, `06-terraform/`, and `08-aws-saa/` use expanded structure.

## Documentation standards

- Markdown only — no HTML, no Word, no PDF inside the repo
- Code blocks must specify language: ```bash ```yaml ```hcl ```json
- Tables must have consistent alignment
- Task checkboxes: `- [ ]` and `- [x]` (not `* [ ]`)
- Tool names in backtick inline: `kubectl`, `ArgoCD`, `Vault`
- No emojis in section headers; status icons (✅ ⏳ ❌) only in tables

## Lab structure

Every lab must include:
1. **Objective** — what this lab demonstrates
2. **Prerequisites** — what must be ready
3. **Steps** — numbered, verifiable commands
4. **Verification** — expected output
5. **Cleanup** — how to undo (if applicable)

CKA labs use `kubeadm` clusters, NOT EKS. Keep them in `labs/kubernetes-cka/`.

## ADR rules

- New ADRs use the next sequential number: `0005-title.md`
- Status values: `Proposed` | `Accepted` | `Deprecated` | `Superseded`
- Update `adr/README.md` table when adding a new ADR

## Cheatsheet rules

- One file per tool in `cheatsheets/`
- Include a last-updated date and version context at the bottom
- Prefer real commands over theory — everything must be runnable

## PROGRESS.md rules

- NEVER overwrite existing weekly entries
- Only append new weeks at the end of the file
- Fixed template format — do not modify its structure
- Update certification table status column only (not target dates)

## CHANGELOG.md format

```
## vX.Y — YYYY-MM
- Change description
```

Minor version bump for new modules; patch for corrections.

## What the agent must NOT do without confirmation

- Delete or overwrite existing modules
- Change the folder structure defined in README.md
- Add executable scripts outside `scripts/`
- Modify PROGRESS.md entries already recorded
- Switch the language of existing content to Spanish
