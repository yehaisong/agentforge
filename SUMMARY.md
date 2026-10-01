# How I used AI to build PartsHub and CBPedia

I used AI agents as development collaborators across planning, design, coding, debugging, testing, and release preparation. I supplied the product goals, domain knowledge, and feedback on the working applications. Agents translated that direction into code and documentation, investigated failures, and helped preserve context between sessions.

## PartsHub

PartsHub turns robotics-club operations into an application for parts catalogs, teams and allowances, procurement, inventory, kit issuance, imports, and reporting. The repository records phased implementation work, an ASP.NET Core/EF Core application, and a continuing SvelteKit frontend migration. Project instructions capture club scoping, service reuse, test conventions, and the boundary between MVC rendering and JSON APIs.

My approach evolved from building the foundation to refining real workflows: purchasing estimates, purchase-order creation, inventory terminology, modal interactions, and report usability. Build and test tasks support the local development loop; GitHub Actions configure backend and frontend validation and Azure release deployment.

Sources at the inspected revision: [README](https://github.com/yehaisong/partshub/blob/0365be7e620e0427b036db9fac62abf9d5bf9f63/README.md), [progress](https://github.com/yehaisong/partshub/blob/0365be7e620e0427b036db9fac62abf9d5bf9f63/docs/progress.md), [Copilot instructions](https://github.com/yehaisong/partshub/blob/0365be7e620e0427b036db9fac62abf9d5bf9f63/.github/copilot-instructions.md), [migration pattern](https://github.com/yehaisong/partshub/blob/0365be7e620e0427b036db9fac62abf9d5bf9f63/docs/frontend_api_migration_pattern.md), [CI](https://github.com/yehaisong/partshub/blob/0365be7e620e0427b036db9fac62abf9d5bf9f63/.github/workflows/ci.yml), [release workflow](https://github.com/yehaisong/partshub/blob/0365be7e620e0427b036db9fac62abf9d5bf9f63/.github/workflows/release_azure_partshub.yml).

## CBPedia

CBPedia is a React/TypeScript Bible-study application using the existing ITIS API. Recorded work covers scripture reading, commentary, cross-references, timelines, maps, multilingual UI, search, study plans, and subsequent reader enhancements.

My saved prompts show iterative collaboration: specifying side-by-side panels and a resizable splitter, tuning spacing and icons, correcting verse identifiers, checking navigation and highlights, and asking agents to investigate broken behavior. Agents also developed an API sweep and report viewer to make payloads, responses, and failures easier to inspect. Agent rules, architecture decisions, work logs, and a synchronized changelog preserve project knowledge. GitHub Actions configure linting, tests, production builds, and FTP release deployment.

Sources at the inspected revision: [agent rules](https://github.com/Imm-Tech-Info-Svc/cbpedia/blob/669041c80e1c1bbe19bed17906bbf1986c85b8d1/AGENTS.md), [session prompts](https://github.com/Imm-Tech-Info-Svc/cbpedia/blob/669041c80e1c1bbe19bed17906bbf1986c85b8d1/docs/session_prompts.md), [work log](https://github.com/Imm-Tech-Info-Svc/cbpedia/blob/669041c80e1c1bbe19bed17906bbf1986c85b8d1/docs/work_log.md), [architecture](https://github.com/Imm-Tech-Info-Svc/cbpedia/blob/669041c80e1c1bbe19bed17906bbf1986c85b8d1/docs/mvp_architecture_brief.md), [API testing record](https://github.com/Imm-Tech-Info-Svc/cbpedia/blob/669041c80e1c1bbe19bed17906bbf1986c85b8d1/docs/test_completed_tasks.md), [CI/release workflow](https://github.com/Imm-Tech-Info-Svc/cbpedia/blob/669041c80e1c1bbe19bed17906bbf1986c85b8d1/.github/workflows/ci.yml).

## From individual prompts to a reusable framework

The reusable pattern is to make the agent's context explicit: product specifications, architecture constraints, task acceptance criteria, relevant verification commands, and records of decisions and failures. This supports focused roles for planning, design, implementation, review, debugging, issue coordination, and release work.

A separate [GitHub issue runner](https://github.com/yehaisong/gh-automation/blob/83272cc5643cac43805904f911d706ca36b22e54/README.md) documents label-based issue claiming, isolated worktrees, Codex execution, optional tests, and draft PR creation. Its existence demonstrates an automation capability; the inspected evidence does not establish that it ran work for both apps.

This summary is based on local repository documentation, workflow configuration, and commit subjects inspected on October 1, 2026. Workflow files establish configured behavior, not successful live deployments. Some planning documents are historical and conflict with later implementation; current code and current project instructions must resolve those differences. AgentForge is a new synthesis of those practices, not a claim that formal skills or all seven agent roles previously existed. Source links may require access to the respective repositories.
