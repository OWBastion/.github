# Repository ownership

Confirm current ownership in the repository's live guidance before making a cross-repository change. This map routes work; it does not copy the owners' current contracts or status.

| Concern | Owner |
| --- | --- |
| Gameplay, Workshop/OverPy source, game-side UI, builds, and releases | `OWBastion/Bastion` |
| Business metadata, identities, submissions, evidence, review, grants, Portal/admin behavior, and platform APIs | `OWBastion/owbastion.com` |
| QQ ingress, channel normalization, commands/replies, deduplication, and notifications | `OWBastion/qqbot` |
| Screenshot recognition evidence, confidence/warnings, and OCR model lifecycle | `OWBastion/ocrkit` |
| Stable organization policy and routing | `OWBastion/.github` |
| Reusable internal agent procedures and discovery metadata | `OWBastion/.agents` |
| Public, portable Overwatch and Workshop skills | `OWBastion/overwatch-ai-skills` |

For Workshop development, `workshop-rs` owns canonical Workshop semantics and APIs, source-language implementations such as `opy-rs` own their language semantics, and Wright is the developer/agent tooling surface where its current capabilities apply. Route a defect to its semantic or implementation owner; do not copy Workshop catalogs or semantic truth into Bastion or organization policy.

Change authoritative contracts at their owner. Integrate consumers in their own repositories and verify the resulting boundary. Resolve ownership changes explicitly before moving or duplicating responsibility.

The platform/Bastion content and build boundary is owned by `Bastion` (`docs/agents/ecosystem-platform-boundary.md`) and `owbastion.com` (`docs/product-rules/integrations-and-workflows.md`); resolve it there rather than from organization policy.
