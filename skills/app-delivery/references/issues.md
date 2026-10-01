# Issue coordination mode

Inspect existing issues and project conventions when access is available and relevant. Draft locally when publication is not requested or external access is unavailable. Use [../assets/issue.md](../assets/issue.md) for a concrete implementation-ready draft.

An issue should state the problem, reproduction or user scenario, desired outcome, scope, acceptance criteria, dependencies, and validation. Link existing issue/PR identifiers only when verified. Do not close an issue merely because code was drafted.

For authorized execution, record ownership and current status using the project's conventions. Link implementation and check evidence. A draft PR or passing tests alone does not establish release completion.

If using an automation runner, inspect its configuration and destructive behavior before executing it. Use a dedicated source checkout when required; do not run reset/clean logic against the user's working repository. Apply ready/working/done/failed labels only where those conventions actually exist. On failure, preserve diagnostic artifacts and identify the recovery action; do not loop automatically without a bounded retry policy.

External creation, comments, labels, pushes, and PR changes require authorization from the user's task. This mode also supports read-only inspection and local drafts.
