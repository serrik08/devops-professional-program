# ADR 0001 — Use Markdown as the documentation format

**Date:** 2026-06  
**Status:** Accepted

## Context

This program generates a large volume of technical documentation: module notes, lab instructions, cheatsheets, certification guides, and progress tracking. A format must be chosen that is portable, versionable, and readable without tooling.

## Decision

Use Markdown (.md) as the sole documentation format across the entire repository.

## Rationale

- Renders natively on GitHub without additional tools
- Works with any text editor (VS Code, Obsidian, Vim, Neovim)
- Version-controllable with Git — diffs are human-readable
- Compatible with OpenCode and other AI coding agents
- Can be exported to HTML, PDF, or other formats when needed
- Industry standard for technical documentation (README, wikis, runbooks)

## Consequences

- No Word documents, PDFs, or Notion pages in this repository
- Diagrams are written in Mermaid (inline) or stored as image files in `diagrams/`
- Tables, code blocks, and checklists cover all structured content needs
