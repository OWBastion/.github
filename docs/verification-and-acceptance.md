# Verification and acceptance

Define the behavior claim and the evidence that could show it is wrong. Verify against an accepted contract, an independent reference, reviewed evidence, or an observable boundary outside the implementation under test. Independent verification does not require another agent; independence comes from the authority used.

For material semantic, lifecycle, gameplay, public-contract, privacy/security, cross-service, or recognition changes, attempt to falsify the key claim with a plausible failure case. Where practical, temporarily remove, invert, or simplify the key behavior and confirm that the chosen check exposes the regression. Do not add permanent production interfaces or scaffolding solely for this exercise.

Keep necessity review separate from correctness verification. Ablation asks whether a newly proposed mechanism is needed while the accepted requirement still holds. Falsification asks whether the implementation is correct. Passing one does not establish the other.

Map acceptance criteria to evidence at the relevant boundary. Local tests, builds, hosted CI, review approval, merge, deployment, and production behavior are separate states. Report only the states actually observed. A green check, test count, or successful build does not by itself establish correctness, review approval, deployment, or production behavior.
