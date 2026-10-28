# Documentation management

Documentation uses progressive disclosure so humans and agents load the smallest current context a task needs.

## Layout

Durable documentation belongs under `docs/`. Repository-root files are limited to entry points and tool-required files (`README.md`, `AGENTS.md`, `CLAUDE.md`, legal files). Each repository with durable documentation provides `docs/README.md` as its index. Skill files and generated files stay where their tooling requires.

Keep each document to one responsibility: purpose and boundary, the current contract in brief, and links to narrower documents. Split when a document holds independently loadable responsibilities. Route to the owning document instead of duplicating a contract to improve discoverability.

## Authority and history

Keep separate: current durable contracts, decision history, current implementation and tests, and mutable state in Issues, PRs, CI, and releases. Current documentation describes the current contract; Git history preserves history. Do not keep stale prose as an archive.

## Agent guidance and skills

`AGENTS.md` carries durable routing, ownership, and invariants; it must not become a manual or copy policy from its owner. Entry files for specific tools import `AGENTS.md` and add only tool-specific guidance.

A skill's `description` is its activation contract: what it does, when to use it, indirect situations that should still route to it, and what it must not be used for. Skills hold procedure and point to the owning policy rather than copying it. When two skills would activate on the same ordinary prompt, clarify their boundary.

## Lessons and retrospectives

A lessons or retrospective file is a staging area, not a policy store. Promote each recurring lesson to its owner: a check or test when a machine can detect the mistake, otherwise the owning policy, repository guide, or skill. Then remove the entry, and delete the file when it is empty. Why: a lesson that exists only in a lessons file is not loaded when the mistake recurs.

## Synchronization and drift

A change to supported behavior, a public contract, ownership, or workflow updates the owning documentation in the same change; implementation and review check this explicitly. Search all documentation for statements about the changed behavior, not only the document you expect to own it, because the same claim is often repeated in architecture, format, and interface documents. Periodically compare documentation with current reality (after migrations, ownership changes, or when a contradiction appears) and fix the owning document rather than copying status elsewhere. Restructuring documentation must preserve meaning unless the task explicitly changes the contract.
