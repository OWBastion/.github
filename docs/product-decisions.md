# Product decisions

Decisions the owner has repeatedly made on player-facing and platform design. Apply them when you propose a design; unresolved product behavior still goes to the owner ([agent guidance](agent-guidance.md#respect-authority-and-responsibility)).

## Show outcomes, not mechanisms

- Tell players what happened to them: passed or not, XP gained, title earned. Do not label content with internal states such as "valid run" or "verified" when only verified content can appear.
- Do not reveal anti-tamper rules, expected values, or detection logic in messages. Tolerate small deviations in validation instead of publishing the threshold.
- Explain an internal concept (such as a draw-algorithm term) in player language, behind an info icon, or drop it. Players do not know the algorithm.
- Prefer an icon, color, or tag to repeated explanatory text. Remove units and words that the number or layout already implies.

## Place a feature by how often it is used

- A low-frequency feature is a secondary interaction inside an existing surface (a card, a menu, a map editor). It does not get its own page section or a large block.
- Put a setting where its subject lives (a map setting with the map), and do not split one action across two screens.
- Keep one place per action. A lifecycle that needs edits in two screens is mis-modeled.

## Model state from the real business flow

- One fact has one state. Remove intermediate states that no actor can act on or that only record plumbing (for example "uploading", "received").
- Derive a state from existing facts when possible, such as an end time, instead of storing a second flag.
- A manual administrator action never depends on automatic state.

## Reduce the operator's work

- Prefer choosing to typing. Offer options, not free input, for bounded values such as expiry or use count.
- Derive a field from data already entered (a version from a date, a window from an end time) instead of asking again.
- Design repeated review for bulk action. If confirming 39 items takes 39 × 3 clicks, change the interaction.
- Separate steps that can fail or run long (review, correction, confirmation, grant) so a timeout in one does not leave the others in doubt.

## Keep history

- "Removed" or "ended" means no longer active, not deleted. Keep ratings, grants, and records of removed items.
- Data that looks like junk can be migration output (for example guests merged into one user). Check provenance before you delete or "clean" it.

## Redesign when you migrate

- When you merge or port a feature, restate the requirement and design it for the new surface. Do not copy the old implementation.
- Use trusted test cases as the contract between old and new implementations.

## Prototype in use

- Iterate a prototype on a real screen with small feedback steps. A prototype that never meets real use only shows the design, not the workflow.
- Check a layout or runtime assumption with a minimal probe (for example one in-game HUD element) before you design around it.

## Name by generating options

- For player-facing names, generate many candidates from different angles, then pick one. A good name ties to the event or background, is memorable enough to spread, and is fun to wear.
