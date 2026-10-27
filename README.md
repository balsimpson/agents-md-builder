# AGENTS.md Builder

A skill for creating, improving and auditing repository instructions for coding agents. It favors concise, verified guidance over large generated documentation.

## What it does

- Creates or updates `AGENTS.md` using repository evidence.
- Audits existing instructions without changing files, then reports a scored, prioritized assessment.
- Keeps a concise `HANDOFF.md` for ongoing work and a human-readable roadmap in an existing document or tracker.
- Reuses existing documentation and checks instructions against the target agent's loading behavior.

## Install in Hermes Agent

```bash
hermes skills install balsimpson/agents-md-builder/skills/agents-md-builder
```

Then ask Hermes, for example: `Use agents-md-builder to audit this repository.`

The skill and its reference files are also available in [`skills/agents-md-builder`](skills/agents-md-builder/) for other agents that support the Agent Skills format. Consult your agent's documentation for installation and instruction-file discovery.

## License

MIT. See [LICENSE](LICENSE).
