# Review mode

Inspect the requested diff or implementation and enough surrounding code to establish actual behavior. Prioritize correctness, authorization/scoping, accounting and persistence invariants, API compatibility, asynchronous state, and meaningful missing regression coverage.

For each actionable finding, provide severity, file and line, a concrete trigger, consequence, and supporting reasoning. Distinguish confirmed defects from hypotheses requiring reproduction. Avoid treating personal style preferences as defects.

Run focused non-mutating checks when they help resolve uncertainty. A clean build does not establish functional correctness. If no actionable findings are supported, say so and state material inspection or test limits.

Do not edit code, post review comments, or change PR state during a review-only request unless those actions are separately authorized. When implementing and self-reviewing, describe verification accurately; do not claim an independent review unless one occurred.
