# ADR 0004 — Use OpenCode + Gemini as the AI coding agent

**Date:** 2026-06  
**Status:** Accepted

## Context

Writing and maintaining 12 modules, 6 certification guides, 30+ labs, and supporting documentation over 12 months is a significant content workload. An AI coding agent can accelerate drafting, maintain consistency, and enforce structure across sessions.

## Decision

Use OpenCode (open-source terminal agent) configured with Google Gemini 2.5 Pro as the primary AI assistant for this repository.

## Rationale

- OpenCode is provider-agnostic — avoids vendor lock-in to a single AI subscription
- Gemini 2.5 Pro has strong performance for technical documentation and code generation
- OpenCode supports AGENTS.md and Skills, allowing the agent to learn project conventions
- BYOK (Bring Your Own Key) model means cost scales with actual usage, not a flat subscription
- Skills written for this project are portable to other agents (Claude Code, Codex, etc.)

## Alternatives considered

- **Gemini CLI** — retired by Google on June 18, 2026 for free/Pro users; replaced by closed-source Antigravity CLI. Not viable.
- **Claude Code** — strong alternative, but requires Anthropic subscription. OpenCode supports Claude via API key if needed.
- **Manual only** — not feasible for the documentation volume this program requires.

## Consequences

- `.opencode/` directory is committed to the repository with agent config and skills
- AGENTS.md is the primary context file for all agent sessions
- Three custom skills are maintained: `markdown-docs`, `devops-conventions`, `progress-tracker`
- Agent sessions use Plan mode before Build mode to avoid unintended file changes
