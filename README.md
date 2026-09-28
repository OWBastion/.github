# OWBastion organization governance

This repository is the canonical owner of stable organization-wide engineering policy and repository routing. It defines shared boundaries; owning repositories remain authoritative for product behavior, domain contracts, implementation details, and mutable status.

## Policy routing

| Concern | Read |
| --- | --- |
| Task context, authority, and ownership | [Agent guidance](docs/agent-guidance.md), [repository ownership](docs/repository-ownership.md) |
| Design choices and persistent mechanisms | [Engineering quality](docs/engineering-quality.md) |
| Tests, fixtures, and expected results | [Testing policy](docs/testing-policy.md) |
| Independent evidence and acceptance | [Verification and acceptance](docs/verification-and-acceptance.md) |
| Simplification and removal | [Entropy policy](docs/entropy-policy.md) |
| Commit, pull request, and default-branch boundaries | [PR delivery](docs/pr-delivery.md) |

Load only the guidance relevant to the task. Repository `AGENTS.md` files route here and retain their local ownership, domain contracts, risk routing, and validation commands.

## Ownership boundaries

- `.github` owns durable organization policy and routing.
- `.agents` owns reusable internal agent procedures and discovery metadata.
- `overwatch-ai-skills` owns public, portable Overwatch and Workshop skills.
- Product repositories own their respective behavior, data, contracts, and release state.

Mutable issue state, current versions, capability inventories, model inventories, and rollout status belong in their live owner, not durable policy.
