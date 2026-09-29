# Agent guidance

## Resolve the task from its owners

A short request such as `implement #123` is enough to begin. Resolve the linked Issue, its repository, and the smallest set of current contracts, source, tests, and policy needed to understand the requested outcome. Do not ask the user to repeat context already available in those sources.

Use the Issue and user request to define scope. Read the owning repository's `AGENTS.md` and specialist guidance for the changed surface. Check current behavior and mutable facts in their live source, such as code, Issues, PRs, CI, releases, or deployment records. Do not copy mutable status into durable policy.

Load policy by task concern. Do not preload every organization document or skill. Reusable internal procedures in `.agents` help apply policy; they do not replace it or expand task scope. Public portable skills remain in `overwatch-ai-skills`.

## Respect authority and responsibility

Compare the requested behavior, the accepted owner contract, and current implementation. If they materially disagree, identify the unresolved decision and route it to the product, architecture, compatibility, privacy/security, or repository owner. Agents may choose local implementation details after the contract is settled; they may not self-authorize a new contract or ownership boundary.

For cross-repository work, identify every affected owner. Change authoritative facts and contracts at their owner, then integrate consumers separately and verify the boundary between them. Do not duplicate another repository's truth for implementation convenience.

Continue reversible, in-scope work without routine confirmation. Follow the owning repository's delivery rules. Get the required authorization before destructive actions, production changes, releases, or other external writes that the task and repository rules do not authorize.

## Write for current models

State the outcome, boundaries, and stop conditions; do not script how a model should think. Omit instructions that compensate for older models: "think step by step", scratchpad or show-your-reasoning requirements, verify-twice rules, fixed step sequences where order does not matter, and rules repeated for emphasis. State a rule once with its reason in its owning document; an always-loaded entry file may summarize it in one line and link there.

Why: current models reason before acting and adjust effort themselves. Ritual instructions add output and repeated tool calls without improving results, and repetition makes one rule outweigh others it was not meant to override.

## Keep tool-specific tuning in tool entry files

`AGENTS.md` and the policies it routes to stay tool-neutral so any agent (for example Codex or Claude Code) reads the same contract. Guidance that depends on one harness or model family, such as subagent or model-selection features, belongs in that tool's entry file (for example `CLAUDE.md`), which imports `AGENTS.md` and does not restate or override shared policy.

Why: shared policy stays portable, and tool tuning can change with a model release without editing policy.

## Design skill metadata for discovery

A skill's description is an activation surface visible before its body loads. Front-load task shapes, changed artifacts, and failure signals, including indirect contexts (a dependency bump can be a testing task). Check a new description against natural trigger prompts, indirect ones, and nearby non-triggers.
