# Pull request delivery

Follow the owning repository's `AGENTS.md` and branch rules. Deliver verified implementation work by one of two routes, and choose the route for each change:

- **PR from a non-default branch** when the change alters a domain rule, product behavior, a public contract, a schema or migration, authorization, secrets, CI, or deployment configuration; needs [independent verification](verification-and-acceptance.md); belongs to a cross-repository change; or targets a repository whose rules require a PR. The PR is the shared review surface. Keep its scope, rationale, acceptance evidence, and check results clear.
- **Direct push to the default branch** when the change is small, self-contained, verified locally, and needs no independent review.

When the route is unclear, open a PR. A direct push is also a merge, and in a repository that deploys from its default branch it is also a deployment; it needs the authorization that the owning repository requires for those steps.

A `pre-push` hook gates every direct push to the default branch. The push passes only as a fast-forward of the clean, checked-out commit, and only when the repository's `.githooks-local/pre-push-main` gate passes. A repository without that gate accepts changes only through a PR. When the hook blocks, fix the cause or open a PR. Never bypass the hook, force-push the default branch, or rewrite history unless the user explicitly authorizes it.

Open a PR as ready for review once the work is complete and verified. Use a draft PR only when the work is unfinished.

Handle actionable review findings on the PR. After a review fix, update the affected thread or review record and request follow-up review once the change and its checks are ready. Keep review comments actionable; avoid generic praise or summaries that do not help the author act.

If a change fails independent review twice on the same claim, stop patching that mechanism. Return to the contract and redesign the approach, or report the blocker. Why: repeated local fixes to one flawed mechanism tend to move the defect instead of removing it.

Push with an explicit refspec (`git push origin <branch>:<branch>`) and push only branches the task owns. In a shared checkout, do not switch, rebase, reset, or push a branch that the user or another session owns. Why: an implicit push follows whatever branch is checked out at that moment, and someone else can change the checkout between commands.

Start every branch from the current remote base: the default branch, or the integration branch the task names. A diff that holds files outside the task means the base is stale; update the base and rebuild the branch. Rebase, resolve conflicts, and refresh dependent branches yourself; do not hand them to the user. When changes depend on each other, land the shared one first (contract, schema, catalog), then rebase the dependents. Why: stale bases and unresolved rebases create review noise and coordination work that the author can remove.

Before delivery, review the complete task-owned diff, run the relevant local validation, and report its result accurately. Use an Issue-closing reference only when the implementation satisfies the Issue's acceptance criteria; use a related reference for partial work and state what remains. A commit or open PR does not mean an Issue is remotely closed, a review is approved, or a change is merged.

Keep review, merge, release, deployment, production mutation, and destructive actions distinct. Perform them only when authorized by the user and the repository's applicable operating rules. Report local validation, hosted checks, review, merge, deployment, and production evidence as separate outcomes.
