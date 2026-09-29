# Engineering quality

Start from the accepted contract and the responsibility of the owning component. Prefer the smallest complete design that meets the current requirement and fits the existing architecture.

Before adding persistent state, a service, API, adapter, flag, configuration, compatibility path, behavior-driving metadata, or cross-repository contract, establish the concrete current need. Trace the direct or existing mechanism first. Try removing, deferring, inlining, or merging the proposed mechanism while preserving the requirement. Keep it only when the simpler path breaks a current contract, real workflow, or demonstrated constraint.

Use clear ownership and local control flow. Add layers or extension points only for a present contract or a repeated pattern that the existing design cannot express cleanly. Do not preserve obsolete paths solely for hypothetical compatibility; approved compatibility requirements belong to their contract owner.

Correctness, accepted ownership, and domain constraints take priority over implementation convenience. If meeting the request requires a new product behavior, public contract, security boundary, compatibility policy, or cross-repository ownership decision, route that decision to its owner before implementing it.

Keep durable documentation stable. Versions, issue state, capability counts, rollout status, and other changing inventories remain in their current authoritative sources.
