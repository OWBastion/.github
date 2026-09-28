# Pull request delivery

Follow the owning repository's `AGENTS.md` and branch rules. Where repository guidance requires a pull request, deliver verified implementation work on a non-default branch and use the PR as the shared review surface. Keep the PR's scope, rationale, acceptance evidence, and check results clear. Do not push implementation commits directly to the default branch or rewrite history unless the user explicitly authorizes it.

Handle actionable review findings on the PR. After a review fix, update the affected thread or review record and request follow-up review once the change and its checks are ready. Keep review comments actionable; avoid generic praise or summaries that do not help the author act.

Before delivery, review the complete task-owned diff, run the relevant local validation, and report its result accurately. Use an Issue-closing reference only when the implementation satisfies the Issue's acceptance criteria; use a related reference for partial work and state what remains. A commit or open PR does not mean an Issue is remotely closed, a review is approved, or a change is merged.

Keep review, merge, release, deployment, production mutation, and destructive actions distinct. Perform them only when authorized by the user and the repository's applicable operating rules. Report local validation, hosted checks, review, merge, deployment, and production evidence as separate outcomes.
