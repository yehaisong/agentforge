---
name: app-delivery
description: Carry scoped application work through planning, UI design, implementation, review, debugging, issue coordination, or release preparation using repository-specific constraints and evidence. Use for application delivery tasks that benefit from these workflows, including PartsHub and CBPedia.
---

# Application delivery

Use the relevant role for the user's requested outcome. Roles are modes of work; they do not require separate agents or a mandatory sequence.

## Establish context

Identify the target repository and read applicable agent instructions. Inspect worktree changes and preserve unrelated user work. Determine whether the user requested a change, a review, a diagnosis, issue management, or a release; preserve the boundary throughout the task.

For PartsHub, read [references/partshub.md](references/partshub.md). For CBPedia, read [references/cbpedia.md](references/cbpedia.md). For another repository, discover equivalent architecture, commands, conventions, and release configuration from its own files. Profiles describe inspected snapshots; verify against current repository files before using them.

Resolve conflicts using the user's request and applicable agent instructions, then current runtime code and configuration, then historical plans. Do not treat an old checked box as proof of current behavior or test coverage.

## Route only to relevant guidance

| Requested work | Read |
|---|---|
| Scope, requirements, architecture decisions | [planning.md](references/planning.md) |
| Layout, interactions, responsive UI | [design.md](references/design.md) |
| Build or change behavior | [coding.md](references/coding.md) |
| Assess a diff or implementation | [review.md](references/review.md) |
| Investigate a failure | [debugging.md](references/debugging.md) |
| Draft, update, or execute issue work | [issues.md](references/issues.md) |
| Prepare or perform a release | [deployment.md](references/deployment.md) |

Implementation requests may use several modes, but skip modes that do not materially help. Review-only and diagnosis-only requests do not authorize fixes. Project instructions may require documentation updates even for otherwise small changes.

## Handoffs and completion

Keep the active scope, acceptance criteria, evidence, open questions, and next action explicit when work crosses roles or sessions. Use [assets/handoff.md](assets/handoff.md) when a written handoff is useful. Include file locations and actual command outcomes; distinguish completed, failed, and unrun checks.

For changes, complete the authorized implementation and relevant verification. For reviews, deliver evidence-backed findings. For diagnosis, deliver the cause or the remaining uncertainty and the evidence needed to resolve it. Report material limits honestly.

Issue publication, messages to others, pushes, PR publication, merges, workflow dispatch, and deployment inherit authorization from the task; the skill itself grants no external actions. Continue authorized reversible preparation and ask only for missing decisions or authority that actually prevent completion. Do not retry unchanged external failures indefinitely or initiate unrelated cleanup.

If delegation is authorized and useful, give each agent a concrete scope and ownership boundary, preserve shared acceptance criteria, and have the coordinating agent inspect results and resolve conflicts. Otherwise perform the modes in one agent.
