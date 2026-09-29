# OWBastion organization governance

This repository owns stable organization-wide engineering policy and repository routing. Owning repositories remain authoritative for product behavior, domain contracts, implementation, and mutable status.

- [Workspace agent routing](AGENTS.md): entry point routing agents to the right repository, policy, or skill.
- [Claude Code entry point](CLAUDE.md): imports `AGENTS.md` and adds Claude-specific guidance. Claude Code reads `CLAUDE.md`, so the workspace root needs a `CLAUDE.md` importing its `AGENTS.md` and `@.github/CLAUDE.md`.
- [Documentation index](docs/README.md): all policy documents.

## Ownership boundaries

- `.github` owns durable organization policy and routing.
- `.agents` owns reusable internal agent procedures and discovery metadata.
- `overwatch-ai-skills` owns public, portable Overwatch and Workshop skills.
- Product repositories own their behavior, data, contracts, and release state.

Mutable issue state, versions, capability inventories, model inventories, and rollout status belong in their live owner, not durable policy.

When editing organization guidance, keep repository-specific contracts with their owners and do not create a second policy store in `.agents` or `overwatch-ai-skills`.
