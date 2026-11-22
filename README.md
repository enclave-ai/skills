# Enclave Skills

Open, portable [Agent Skills](https://agentskills.io) by [Enclave](https://enclave.ai).

## Install

```bash
npx skills add enclave-ai/skills
```

To install a specific skill:

```bash
npx skills add enclave-ai/skills --skill security-context
```

## Available Skills

### `security-context`

Generates and maintains a concise, repo-specific `SECURITY_CONTEXT.md` at the repository root along with a lightweight `AGENTS.md` pointer so coding agents catch more real vulnerabilities and respect security boundaries when writing code.

- **`init`** — Audits the repo and generates `SECURITY_CONTEXT.md` + `AGENTS.md` pointer.
- **`sync`** — Updates `SECURITY_CONTEXT.md` when security-relevant code drifts.
- **`check`** — Verifies freshness and schema compliance in CI or locally via [`scripts/detect-drift.mjs`](./skills/security-context/scripts/detect-drift.mjs).

## Repository Layout

- [`skills/security-context/`](./skills/security-context/SKILL.md) — Portable Agent Skill (`SKILL.md`, [`references/schema.md`](./skills/security-context/references/schema.md), [`scripts/detect-drift.mjs`](./skills/security-context/scripts/detect-drift.mjs))
- [`SPEC.md`](./SPEC.md) — `SECURITY_CONTEXT.md` specification and design rationale

## License

[MIT](./LICENSE)
