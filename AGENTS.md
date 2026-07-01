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
| Competency roadmaps | `learning-paths/<competency>/` (courses, certs, projects) |
| Module study notes & labs | `modules/<NN>-<name>/` (theory, labs, notes) |
| Career & Cert evaluations | `career/` (matrix, framework) |
| Weekly logs | `weekly/week-<NN>.md` |
| Quick reference | `cheatsheets/<tool>.md` |
| Architecture decisions | `adr/<NNNN>-<title>.md` |
| Reusable scripts | `scripts/` |

Never create files outside these locations without explicit confirmation.

## Module vs Learning Path structure

- **`learning-paths/`**: The roadmap. Defines *what* to study, in what order, which certifications to take, and which projects demonstrate the competency.
- **`modules/`**: The actual content. Theory, hands-on labs, command outputs, and study notes.

Every module must use a folder structure:
```
modules/07-gitops-argocd/
    README.md          - main theory
    labs/              - lab markdown files
    manifests/         - example YAML
```

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

## Weekly Tracking (`weekly/`)

- Add new entries as `weekly/week-<NN>.md`
- Append links to `weekly/README.md`
- Keep the exact same structure for new weeks
- NEVER overwrite or modify past weeks' contents unless fixing typos

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
