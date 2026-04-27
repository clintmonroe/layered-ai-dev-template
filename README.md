# layered-ai-dev-template

A spec-first, architect-led AI development workflow. Claude designs. Local models build. An independent agent reviews before anything merges. Git is the source of truth.

This isn't an autonomous agent framework. The goal is discipline, traceability, and repeatable delivery — with a human approving every decision that actually matters.

---

## How it works

Every feature follows the same chain:

```
constitution → spec → plan → tasks → tests → implementation → review → lesson
```

The **Architect** (Claude Opus) owns everything before a line of code is written: requirements, specs, ADRs, task decomposition, acceptance criteria. It does not write production code.

The **Implementer** (Qwen via Ollama, driven by Aider) executes one bounded task at a time against a spec it didn't write, until the tests pass. Nothing else.

The **Adversary** (Codex CLI) reviews the diff independently before merge. Security, correctness, architecture compliance, failure modes. It looks for problems; it doesn't fix them.

**Git** is immutable memory. Reversibility, auditability, no hidden state.

---

## What this is built on

- `spec-kit` for the spec/plan/tasks artifact chain
- Claude Code for orchestration and architecture
- Aider + Ollama + Qwen3.6 for local implementation
- `codex-plugin-cc` for adversarial review
- Markdown with frontmatter for project memory — no vector DB, no context bloat

All of it is thin and replaceable. The process is the point, not the tooling.

---

## Core assumptions

Code written before tests exist is suspicious. The model that writes the code shouldn't review its own work. Long-term consistency comes from structure, not chat history. Small, explicit tasks outperform giant prompts.

Prompts are replaceable. Process is the moat.

---

## Status

Intentionally minimal. Designed to evolve through actual feature delivery.

The first goal: run one real feature end-to-end. Everything else is secondary.

---

## License

MIT. See `CREDITS.md` for upstream attribution.
