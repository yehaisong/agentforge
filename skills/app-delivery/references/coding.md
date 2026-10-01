# Implementation mode

Trace the affected path from user interaction through state, API/service boundaries, and persistence. Reuse established service and component boundaries. Changes to contracts must align producers, consumers, validation, and documentation that governs future work.

Preserve repository-specific invariants such as tenant scoping, stock accounting, semantic identifiers, authentication, and asynchronous navigation ordering. Do not generalize one application's rules into another application's architecture.

Implement the smallest coherent change satisfying the acceptance criteria. Add meaningful regression coverage for changed logic or risky boundaries; avoid tests that merely repeat implementation details. For minor presentation changes, relevant static checks and rendered inspection may suffice.

Run checks appropriate to the touched layers using the current project scripts. Report failed checks and distinguish pre-existing failures using evidence. Update required work logs, migration guidance, or decision records. Finish with changed behavior, validation, and remaining limits.
