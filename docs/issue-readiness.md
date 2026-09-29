# Issue readiness and implementation preflight

Issues describe the problem or desired behavior, scope, relevant non-goals, constraints, observable acceptance criteria, and dependencies. They are not implementation specifications unless a technical structure is itself an accepted contract. Do not manufacture content for a section that does not apply; if material information is unknown, the Issue needs a decision, not an implementation.

## Verifiable outcomes

Substantive behavior work is ready when its acceptance criteria form a practical verification boundary: what must be true, which check would fail if it were wrong, and whether that failure is attributable to this task. The Issue need not name test files. If criteria are too vague to derive a check that could fail, the acceptance boundary is undecided and the Engineer does not invent it. If the owning repository has no harness for the behavior, building it is a separate prerequisite. When the outcome is not machine-verifiable (documentation, guidance), the criteria name the review or reference check that decides completion.

Size tasks by an independently verifiable outcome, not by lines or steps. Fold implementation-only fragments into the behavior they serve.

## Preflight

Before changing code in substantive work, compare:

- the Issue contract, including comments, parent, and linked work;
- the current authoritative contract from repository guidance and durable documentation (decision records are not proof of current behavior);
- current implementation reality: code, consumers, tests, and dependency boundaries, inspected far enough to be decisive.

If they materially disagree, report the unresolved product, architecture, compatibility, or ownership decision instead of choosing a design. Also identify the checks that decide completion. When the three align, implement under [engineering quality](engineering-quality.md) and verify under [testing policy](testing-policy.md) and [verification](verification-and-acceptance.md).

## Contract continuity for boundary migrations

When a change replaces, hides, or retires a public or authoritative boundary (API, schema, protocol, generated contract), every capability of the previous contract must be exactly one of:

1. **Preserved** — verified directly through the replacement boundary.
2. **Approved removal or change** — backed by an owner decision, not dropped as a side effect.
3. **Transferred** — moved to a named new owner and handoff boundary.

Checks through a retired or compatibility-only path do not prove the replacement complete.
