# Release mode

Determine the actual target environment, release trigger, revision, build artifact, configuration requirements, and relevant checks from current project files. Read the applicable project profile for known branch and provider conventions.

For release preparation, produce a concrete release record using [../assets/release.md](../assets/release.md). Check whether publishing or dispatching the release branch automatically deploys; those actions are deployment actions when they trigger production delivery.

Before an authorized deployment, verify the artifact's checks and relevant environment prerequisites. Account for migrations, startup seeding, static frontend assets, and recovery steps where they affect this release. Do not assume artifact rollback also reverses database changes.

Use the existing supported release mechanism. Track actual workflow results and verify the deployed behavior when access permits. Distinguish prepared, triggered, completed, and verified states. A workflow file or uploaded artifact is not evidence of a successful deployment.

If deployment fails, retain the revision and diagnostic evidence, investigate the failure, and retry only after resolving its cause or confirming a transient failure within the authorized scope. Expanding infrastructure, rotating credentials, deleting data, or changing providers requires its own scope and authority.
