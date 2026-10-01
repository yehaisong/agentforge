# Working on AgentForge

AgentForge packages reusable instructions, project profiles, and templates. It does not contain application runtime code.

- Keep generic workflow guidance in `skills/app-delivery/SKILL.md` and its role references. Keep application-specific constraints in the corresponding project profile.
- Preserve the distinction between historical evidence, configured automation, and verified outcomes in `SUMMARY.md`.
- Make documentation portable: use relative package links and placeholder device paths; use revision-pinned GitHub links for external source evidence.
- Keep references and assets inside the skill folder so it can be installed as one unit. Do not assume a particular host's tools or install location.
- Check local Markdown references and YAML metadata after edits. If the skill-creator validator is available in the environment, run it on `skills/app-delivery`; it is an optional authoring tool, not a package runtime dependency.
- Do not include credentials, copied application configuration, or personal environment files in public changes.
- A change to the framework does not authorize issue publication, application changes, or deployments in the example projects.
