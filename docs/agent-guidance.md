# Agent guidance

## Resolve the task from its owners

A short request such as `implement #123` is enough to begin. Resolve the linked Issue, its repository, and the smallest set of current contracts, source, tests, and policy needed to understand the requested outcome. Do not ask the user to repeat context already available in those sources.

Use the Issue and user request to define scope. Read the owning repository's `AGENTS.md` and specialist guidance for the changed surface. Check current behavior and mutable facts in their live source, such as code, Issues, PRs, CI, releases, or deployment records. Do not copy mutable status into durable policy.

Load policy by task concern. Do not preload every organization document or skill. Reusable internal procedures in `.agents` help apply policy; they do not replace it or expand task scope. Public portable skills remain in `overwatch-ai-skills`.

## Respect authority and responsibility

Compare the requested behavior, the accepted owner contract, and current implementation. If they materially disagree, identify the unresolved decision and route it to the product, architecture, compatibility, privacy/security, or repository owner. Agents may choose local implementation details after the contract is settled; they may not self-authorize a new contract or ownership boundary.

For cross-repository work, identify every affected owner. Change authoritative facts and contracts at their owner, then integrate consumers separately and verify the boundary between them. Do not duplicate another repository's truth for implementation convenience.

Continue reversible, in-scope work without routine confirmation. Follow the owning repository's delivery rules. Get the required authorization before destructive actions, production changes, releases, or other external writes that the task and repository rules do not authorize.
