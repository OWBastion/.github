# Content publishing and build contract

This document defines the cross-repository boundary for platform-managed content (events, maps, achievements, titles) and Bastion builds. It fixes responsibilities and invariants. Implementation shape, current phase, and rollout status belong to the owning repositories, Issues, and their live contracts. Where current reality differs, keep the boundary and route the difference to the owner rather than choosing a design through implementation convenience.

## Boundary

The platform decides which content exists, how it is presented, when it enters a version, and which version is officially released. Bastion decides how that content is implemented in the game, how it compiles, and whether it satisfies Workshop performance and stability limits.

Why: the platform can declare content but cannot judge Workshop cost, and Bastion can implement content but should not own player-facing metadata. Crossing the line makes either side a second source of truth.

| Concern | Owner |
| --- | --- |
| Content entities, stable IDs, player-visible names, descriptions, categories, status, icons, relations | `owbastion.com` |
| Draft, change set, candidate, release lifecycle; current and next release pointers; release history and rollback basis | `owbastion.com` |
| Initiating a Bastion build and showing its status | `owbastion.com` |
| Per-event Workshop behavior, OverPy/Workshop mapping, arrays, macros, variable layout, performance and Element limits | `Bastion` |
| Verifying that content the platform enables has an implementation; deterministic build output; build diagnostics | `Bastion` |
| Consuming published content (QQ, OCR, web front end, agents) | Each consuming repository, from the platform's published data |

The platform does not describe or execute event behavior, generate Workshop or OverPy code, or edit Bastion source. Consumers do not keep independent copies of content truth.

## Lifecycle concepts

- **Draft**: an editable workspace that may be incomplete and never affects the current release.
- **Change set**: the selection of draft changes intended for the next release. Unselected draft edits do not enter it.
- **Candidate**: an immutable snapshot generated from a change set, used for review, testing, preview, and builds. Adjustments produce a new candidate; a candidate is never edited in place.
- **Release**: an immutable version activated after a successful build. It records the content snapshot, the Bastion code version, the build result and artifact identity, the time, the operator, and a change summary. One release is current at a time and history is kept.

## Invariants

- Content is identified by a stable, unique ID. Bastion binds implementations to IDs, not to names or ordering.
- Bastion builds a specified candidate, never an unspecified "latest".
- A build binds one content snapshot to one Bastion code version and is deterministic for that pair.
- A release is activated only after its build succeeds. A failed build leaves the current release unchanged.
- Release history supports rollback and rebuild.
- Bastion reads only the data it needs, and remains buildable and testable locally without the platform.
- Previewing next-version content on the website is display only. It must not feed achievement progress, screenshot submission, automatic review, title grants, rankings, or statistics. Switching content inside the game requires a separate Bastion test build of the candidate.
- Any new step considers failure state, rollback, and history.

## Data model

Model content, not Workshop execution. Full description text, tags, and search data are fine, and a few stable parameters may be exposed when a real need exists. Do not require every effect to be structured, and do not build a general behavior DSL.

## Non-goals

The platform does not take over all event parameters, maintain implementation capability tags, or open automatic update PRs against Bastion. Do not migrate all historical files or connect every repository at once.

Any design beyond these boundaries must first show why it is necessary.

## Working with existing systems

Reuse each repository's current architecture and migrate incrementally. Keep the cross-repository protocol small, stable, and versionable. Other repositories first check whether they duplicate content data, and connect to the platform only when that removes a duplicate source, improves freshness, or improves consistency. Apply the ownership and delivery rules in [repository ownership](repository-ownership.md) and [verification](verification-and-acceptance.md); local build, hosted build, activation, and production behavior are separate states.
