# OWBastion Workspace Agent Routing

This is the organization-level routing entry point. It carries durable constraints and routing; it is not a technical manual.

Repository-local `AGENTS.md` files specialize contracts for their own repository. They must not duplicate shared policy, but may add stricter or domain-specific requirements that take precedence locally. Tool-specific entry files such as [`CLAUDE.md`](CLAUDE.md) load this file and add only tool-specific guidance.

The user request and linked Issue set task scope. Identify the owning repository, read the linked Issue (with comments, parent, and linked work) and the nearest `AGENTS.md`, then load only relevant policy or skills. A short request such as `implement #123` is sufficient; see [Issue readiness](docs/issue-readiness.md) for the preflight. Substantive behavior work also needs the checks that will decide completion identified before editing.

## Repository routing

Confirm current ownership in live guidance before substantial work; see [repository ownership](docs/repository-ownership.md).

| Concern | Repository |
| --- | --- |
| Gameplay, Workshop/OverPy source, game-side UI, builds, releases | `Bastion` |
| Business metadata, identities, submissions, evidence, review, grants, Portal/admin, platform APIs | `owbastion.com` |
| QQ ingress, channel normalization, commands/replies, deduplication, notifications | `qqbot` |
| Screenshot recognition evidence, confidence/warnings, OCR model lifecycle | `ocrkit` |
| Stable organization policy and routing | `.github` |
| Reusable internal agent procedures | `.agents` |
| Public portable Overwatch/Workshop skills | `overwatch-ai-skills` |

For cross-repository work, read every affected repository's `AGENTS.md`, change the authoritative contract at its owner, integrate consumers separately, and verify the boundary between them.

## Policy routing

Load policy only when its concern is relevant. Do not preload all of it.

| Task concern | Load |
| --- | --- |
| Task context, authority, self-authorization | [`docs/agent-guidance.md`](docs/agent-guidance.md) |
| Ownership and cross-repository boundaries | [`docs/repository-ownership.md`](docs/repository-ownership.md) |
| Issue readiness, verifiable outcomes, implementation preflight, boundary-migration continuity | [`docs/issue-readiness.md`](docs/issue-readiness.md) |
| Design choices, persistent mechanisms, comments | [`docs/engineering-quality.md`](docs/engineering-quality.md) |
| Tests, fixtures, expected results | [`docs/testing-policy.md`](docs/testing-policy.md) |
| Independent evidence and acceptance | [`docs/verification-and-acceptance.md`](docs/verification-and-acceptance.md) |
| Simplification, deletion, duplicate truth | [`docs/entropy-policy.md`](docs/entropy-policy.md) |
| Commit, PR, and default-branch boundaries | [`docs/pr-delivery.md`](docs/pr-delivery.md) |
| Durable documentation layout, drift audits, guidance and skill authoring | [`docs/documentation.md`](docs/documentation.md) |
| Simplification, deletion, duplicate truth (procedure) | `.agents/skills/owbastion-reclaim-entropy/SKILL.md` |
| Test necessity, stability, duplication review | `.agents/skills/owbastion-test-design-review/SKILL.md` |
| Independent verification of someone else's material change | `.agents/skills/owbastion-verify-change/SKILL.md` |
| Other workspace skill procedures | `.agents/skills/<name>/SKILL.md`, per [`.agents/README.md`](../.agents/README.md) |

## Global invariants

- Respect ownership: modify authoritative contracts at their owner and never bypass it for implementation convenience.
- Do not self-authorize unresolved gameplay behavior, product behavior, public contracts, ownership changes, compatibility policy, security boundaries, or cross-repository architecture.
- Durable guidance stores stable ownership, contracts, invariants, and routing. Versions, endpoint inventories, feature status, counts, and Issue state live in their authoritative source.
- Do not weaken tests, validation, diagnostics, error handling, or accepted contracts to obtain a green result.
- When replacing or retiring a public or authoritative boundary, verify surviving contracts through the replacement itself ([Issue readiness](docs/issue-readiness.md#contract-continuity-for-boundary-migrations)).
- Do not add abstractions, state, adapters, or extension points for hypothetical needs.

## When to stop

Continue authorized, reversible work without routine confirmation. Stop and ask only when missing information could materially change the outcome, an owner decision is unresolved, the Issue, contract, and code materially conflict, the next action is external or irreversible and unauthorized, or a concrete blocker prevents progress. Finish whatever does not depend on the answer first.

## Final report

Lead with what needs the reader: an open decision, a blocker, or an action needing their authority. Then give the delivered or local state, the independent reference used for verification, and anything you could not confirm, with where you looked. Do not narrate the session.
