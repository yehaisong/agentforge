# AgentForge

An AI-assisted software delivery framework for turning ideas into applications.

A reusable skill and role framework derived from PartsHub and CBPedia. The human supplies product direction and domain judgment; the agent turns scoped requests into reviewable changes with evidence.

- [Experience summary](SUMMARY.md): how AI supported both applications, with source references.
- [Reusable skill](skills/app-delivery/SKILL.md): routing, task boundaries, and completion criteria.
- [PartsHub profile](skills/app-delivery/references/partshub.md) and [CBPedia profile](skills/app-delivery/references/cbpedia.md): project-specific rules and validation.
- [Issue template](skills/app-delivery/assets/issue.md), [handoff template](skills/app-delivery/assets/handoff.md), and [release template](skills/app-delivery/assets/release.md): use when the task benefits from a written artifact.

## Get AgentForge

Clone the public repository on any device with Git:

```bash
git clone https://github.com/yehaisong/agentforge.git
cd agentforge
```

Or [download the ZIP](https://github.com/yehaisong/agentforge/archive/refs/heads/main.zip) and extract it. The framework consists of Markdown and YAML files; using the instructions does not require a build or runtime dependency.

To update a cloned copy, run `git pull --ff-only` inside the repository after saving any local changes.

## Use

In any agent that can read workspace files, start with:

> Read [path-to-agentforge]/skills/app-delivery/SKILL.md and use it to implement [request] in [repository].

Replace `[path-to-agentforge]` with this folder's location on your device and `[repository]` with the application you want to work on. You can keep AgentForge separate from your application repositories.

For review or diagnosis, explicitly say “review only” or “diagnose only.” For another application, supply its repository and use its own instructions and commands; the two included profiles are examples of project-specific context.

AgentForge is not automatically loaded by your application repositories. A skill-aware host can install the complete `skills/app-delivery` folder into its supported skill directory and invoke `$app-delivery`; retain its references and assets. The file-reading prompt above works without installation. Follow your host's current instructions for skill discovery and reload behavior.

Example requests:

- “Use AgentForge to implement this feature in PartsHub.”
- “Use AgentForge to review this CBPedia change; review only.”
- “Use AgentForge to diagnose this navigation failure; diagnose only.”
- “Use AgentForge to prepare an issue draft and release checklist for this application.”

These examples assume you have supplied the skill file or installed the skill in your host.

## Roles and workflow

| Role | Main artifact | Completion evidence |
|---|---|---|
| Planner | Scoped requirement and acceptance criteria | Concrete observable outcomes |
| Designer | Interaction/layout decisions | Loading, empty, error, mobile, and keyboard behavior addressed as relevant |
| Implementer | Code and necessary documentation | Relevant checks and acceptance scenarios |
| Reviewer | Evidence-backed findings | Severity, location, trigger, and consequence |
| Debugger | Reproduction and cause | Evidence distinguishing cause from symptoms |
| Issue coordinator | Issue or local draft with status | Links to implementation and validation |
| Release operator | Release record or deployed artifact | Target, revision, verification, and recovery information |

These are operating modes, not automatically spawned agents. One agent can move between them. Separate agents require authorization from the user or applicable instructions; divide work by concrete ownership and integrate results before claiming completion.

Typical implementation flow: scope → relevant design → implementation → validation/review → authorized release. A small edit may need only implementation and one relevant check. A review or diagnosis ends with findings unless changes are also requested.

External issue writes, messages, PR publication, merges, and deployment require applicable task authorization. Creating this framework grants none of those actions.

## Adapt to another application

Supply the target repository and its agent instructions. The skill discovers its architecture and checks rather than applying PartsHub or CBPedia rules universally. For repeated use, add a focused project profile under `skills/app-delivery/references/` and link it from the skill's context section.

The experience summary links to the original project snapshots on GitHub. Access to those source repositories may require separate permission; the framework itself is self-contained.
