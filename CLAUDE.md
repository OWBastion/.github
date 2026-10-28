# OWBastion for Claude Code

@AGENTS.md

This file adds only what is specific to Claude Code. Where anything here seems to differ, `AGENTS.md` and the policy it routes to take precedence.

## Long runs

- The finish line is the Issue's acceptance criteria plus delivery under the owning repository's rules. Work to it without check-ins; stop only under [When to stop](AGENTS.md#when-to-stop).
- Gather starting context in one batch: the Issue with its comments, parent, and linked Issues and PRs, the nearest `AGENTS.md`, and the code the change touches. Make independent reads and searches as parallel tool calls.

## Handoff between sessions

- When work passes between sessions (implementer, reviewer, orchestrator), write findings to a file in the task's ignored scratch directory. Post a PR comment that states what changed and that the PR is ready for review; with no review thread, that comment is the handoff signal.
- When an Issue is delivered, blocked, or reassigned, stop working on it and move to the next task.

## Subagents

- Split broad read-only investigation across subagents only when it divides cleanly by owner, such as finding every consumer of a boundary across repositories. Give each a self-contained prompt and require evidence (paths with line numbers or command output); check that evidence before accepting a conclusion.
- Do not use a subagent to verify or review your own change; independence comes from the reference used, not from another agent.
