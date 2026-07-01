# ADR 0003 — Use English as the primary language

**Date:** 2026-06  
**Status:** Accepted

## Context

The author's native language is Spanish. The target employers are international companies (US, Europe, global remote). The entire DevOps/SRE toolchain (Kubernetes, AWS, Terraform, ArgoCD) is documented in English.

## Decision

All public-facing content in this repository is written in English:
- README, ROADMAP, CHANGELOG
- Module files, certification guides, lab instructions
- Cheatsheets, ADRs, project documentation
- Code comments and commit messages

Personal study notes (`notes/`) may be written in Spanish if that aids comprehension.

## Rationale

- GitHub is a global platform; English maximizes reach and credibility
- Recruiters at Amazon, Microsoft, Globant, EPAM, and Canonical read English
- Technical terms (kubectl, namespace, ingress, provider) are English by nature — mixing languages produces awkward output
- Writing in English is itself a practice opportunity for technical communication

## Consequences

- The author commits to writing and maintaining all module content in English
- AI agents (OpenCode + Gemini) are prompted in English for content generation
- Spanish is acceptable for personal notes and internal comments
