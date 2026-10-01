# PartsHub project profile

Snapshot derived from the sibling `partshub` repository on October 1, 2026. Locate that repository from the user's target/workspace; re-read current `.github/copilot-instructions.md`, `README.md`, and applicable agent instructions before acting. The profile is not a replacement for current code.

## Architecture and invariants

ASP.NET Core .NET 10 with EF Core and Identity; MVC/Razor and a SvelteKit frontend under `/app`. Dedicated `/api/*` JSON controllers should share business services with MVC controllers; do not expose Razor partials and redirects as the Svelte contract. Follow `docs/frontend_api_migration_pattern.md`.

Club scoping is central. Inspect current base controllers and access helpers rather than re-deriving scope. Parts derive club ownership through categories. Preserve cookie authentication and antiforgery behavior across Svelte mutations.

Current documented stock source is `Part.QuantityOnHand`; issuance decreases stock, returns increase stock, and handoff confirmation must not decrement again. Verify current entities/services because older plans describe batches and reservations that may no longer apply. Preserve package-versus-unit cost semantics and decimal purchasing quantities.

Startup migrates and seeds the database; account for this in release assessment. Keep seeded-account values and connection secrets out of generated reports.

## Validation

Run the relevant commands from the repository root; verify scripts/project files before use:

```bash
dotnet restore PartsHub.sln
dotnet build PartsHub.sln --no-restore --configuration Release
dotnet test tests/Partshub.Console.UnitTests/Partshub.Console.UnitTests.csproj --no-build --no-restore --configuration Release --verbosity minimal
dotnet test tests/Partshub.Console.IntegrationTests/Partshub.Console.IntegrationTests.csproj --no-build --no-restore --configuration Release --verbosity minimal
```

For frontend changes, from `frontend`: `npm run check` and `npm run build`. Dependencies must already be installed or installed through the environment's permitted mechanism. Unit tests cover services/importers; integration tests cover app routes with temporary SQLite and test authentication. Include club isolation and validation scenarios when changing APIs.

`.vscode/tasks.json` and launch configuration document hot reload, safe builds during debugging, and DLL lock recovery. Prefer those established mechanisms when the failure concerns local debug/build contention.

## Issue and release context

`docs/progress.md` contains issue-linked phases; treat its status as historical until checked against code. CI is `.github/workflows/ci.yml`. The release workflow `.github/workflows/release_azure_partshub.yml` runs backend tests, builds/checks the frontend, publishes .NET, and deploys to Azure Web App `partshub`, Production slot. Pushes to `release_azure` with matching paths or manual dispatch trigger it. Those actions can deploy; preparation alone does not authorize them.
