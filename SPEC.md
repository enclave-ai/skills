# `SECURITY_CONTEXT.md` Specification (v1)

## Purpose

`SECURITY_CONTEXT.md` is a concise, repo-specific security context document placed at the root of a repository for coding agents and engineers. It complements—and never replaces—`SECURITY.md` (vulnerability disclosure policy) and `AGENTS.md` (general engineering instructions).

## Design Goals

1. **O(1) size on any repository:** `SECURITY_CONTEXT.md` MUST NOT grow with codebase size. It documents architectural boundary mechanisms, reusable security primitives, and invariants—never endpoint or file inventories. Hard cap: **≤ 150 lines** (target 60–120 lines).
2. **Repo-specific invariants over generic advice:** Agents already know OWASP checklists. They fail when they miss *this repository's* trust boundaries, blessed helper primitives, upstream deployment guarantees, and Sev-0 invariants.
3. **Progressive disclosure via `AGENTS.md`:** A compact (2–4 line), repo-tailored pointer in `AGENTS.md` directs agents to read `SECURITY_CONTEXT.md` only when touching security-boundary paths or intents—avoiding context bloat on unrelated edits.
4. **Defensive, never an attacker's roadmap:** Records invariants and safe primitives—never live vulnerabilities, exploit paths, credentials, or internal hostnames.
5. **Agentic discovery & legacy ratcheting:** Uses top-down entrypoint tracing + capability search (no brittle language-specific static pre-scanners) and ratchets legacy debt in one line so rules never contradict existing valid code.

## File Format

See [`skills/security-context/references/schema.md`](./skills/security-context/references/schema.md) for the exact v1 frontmatter, 5-section layout, redaction rules, and `AGENTS.md` pointer format.
