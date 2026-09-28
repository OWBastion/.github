# Testing policy

Tests protect observable contracts, regressions, meaningful failure modes, and stable invariants. A code change alone is not a reason to add or retain a test. Select checks for the distinct claim they protect, not to maximize test counts or snapshot implementation structure.

Expected results need an authority independent of the implementation under test: an accepted contract, reviewed evidence, an established reference, or a real regression with suitable provenance. Do not use generated output from the same implementation as its own oracle, or change expectations only to make a new implementation pass. Hard-coded counts, versions, and inventories are appropriate only when that exact value is part of the contract.

Do not add production APIs, visibility, hooks, state, flags, configuration, or architecture solely to expose internals to tests. Prefer the existing public or domain boundary when it expresses the behavior being protected.

Tests, fixtures, snapshots, and fakes are also maintained code. Keep them when they protect a durable claim or distinct failure mode; consolidate, rewrite, or remove them when they duplicate evidence or preserve obsolete behavior. Do not weaken validation, diagnostics, error handling, or accepted contracts merely to make a check pass.

A test result supports only the behavior and boundary it actually exercises. Test count, code presence, and a green suite are evidence summaries, not proof beyond that scope. Domain owners may add stricter rules for expected truth, privacy, lifecycle, compatibility, and failure coverage.
