# ADR 0002 — Repository structure and organization

**Date:** 2026-06  
**Status:** Accepted

## Context

The program covers 12 modules, 6 certifications, multiple labs, projects, and supporting material. A structure is needed that scales without becoming a maintenance burden.

## Decision

Use a flat-first structure with selective expansion for large modules.

- Small modules (Git, Docker, Linux): single `.md` file in `modules/`
- Large modules (Kubernetes, Terraform, AWS): expanded folder structure with sub-directories for labs, notes, manifests, and cheatsheets
- Supporting material lives in dedicated top-level directories: `certifications/`, `labs/`, `projects/`, `cheatsheets/`, `adr/`

## Rationale

- Flat files are easier to navigate and maintain at the start
- Kubernetes alone has 30+ planned labs and needs its own structure
- Top-level directories by concern (not by module) avoid deep nesting
- ADRs document why the structure looks the way it does

## Consequences

- `modules/05-kubernetes/` is the only module with an expanded folder structure initially
- New top-level directories require a corresponding ADR update
- AGENTS.md enforces this structure for the OpenCode agent
