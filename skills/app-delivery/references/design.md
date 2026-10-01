# Design mode

Start from the existing design system, actual page structure, and task-specific user journey. Define the layout and interactions that support the requested behavior; prefer existing components, tokens, and terminology.

For affected interactions, consider loading, empty, error, success, mobile, keyboard/focus, and persisted-state behavior where relevant. Specify which state is local, shared, URL-backed, or server-owned when the distinction affects correctness.

Use a compact sketch or interaction description when it makes a layout decision reviewable. Inspect the rendered result if browser tools are available; otherwise state that visual verification was not performed. A successful build does not establish that the UI looks correct.

Use observed UI problems to drive iteration. Preserve working cross-feature navigation and avoid exposing internal debugging details in product flows unless they help users act on an error.
