# Debugging mode

Establish expected behavior, actual behavior, trigger, and relevant environment. Reproduce through the narrowest useful path, or capture the missing evidence if reproduction is unavailable.

Follow the failure across UI events, state transitions, requests, response normalization, services, and persistence as relevant. Inspect actual identifiers and payload shapes rather than inferring semantics from names. For races, compare event order and stale versus current request state.

Keep a compact hypothesis/evidence record for complex investigations. Use logs that identify scope, request stage, status, and timing without exposing secrets. Distinguish a backend contract rejection from a successful local UI update.

A diagnosis-only request ends with cause and evidence, or bounded uncertainty. If a fix is authorized, correct the cause, reproduce the successful outcome, and use focused regression coverage when warranted. Remove temporary diagnostics unless an intentional user-facing diagnostic feature is requested.
