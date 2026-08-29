# CoreLink Release Policy

CoreLink is one product with multiple release boundaries. Runtime, contracts, Console, SDKs, tools, documentation, and the website may have separate artifacts, but supported claims must reconcile through one product maturity model.

## Maturity

Use: **Scaffold, Experimental, Alpha, Beta, Stable, Deprecated, Planned**.

A tag or package publication does not by itself establish support. Supported releases require the owning repository's release gate plus compatible contract, security, documentation, and operational evidence.

## Product release train

CoreLink runtime consumers that ship as one hosted/self-hosted product experience MUST move through a coordinated release train.

- `platform` is the release-train orchestrator and owns the canonical CoreLink stack version.
- `Console` consumes CoreLink APIs through the supported TypeScript SDK/contract boundary; it must not maintain an independent hand-written public API contract.
- The TypeScript SDK records immutable `api-contracts` provenance and is built/tested against the same accepted runtime contract used by Console.
- Platform and Console release artifacts use the same CoreLink stack version when released as a tested pair.
- A stack release records exact Platform image, Console image, SDK version, contract revision and source SHAs in a machine-readable manifest.
- The floating `latest` channel may be promoted only after the exact-version Platform/Console pair has passed compatibility/integration checks. Component repositories must not independently move `latest` in a way that can create an untested pair.
- Production deployments should prefer an exact `CORELINK_VERSION`; `latest` is a convenience channel, not stronger provenance.

The public API contract has its own compatibility lifecycle. An additive public-contract revision does not need to copy the runtime version number, but every supported stack release must identify the exact contract revision it implements and consumes.

## Version provenance

Released artifacts should identify immutable source and dependency revisions. Generated SDKs and contract consumers must identify the exact contract tag/revision used. Branch names are not release provenance.

Runtime services should expose build metadata sufficient to diagnose compatibility without leaking secrets, including the product/runtime version, API contract revision, and immutable build/source identifier where available.

## Release contents

Where applicable, a release should include:

- version/tag and immutable commit SHA;
- maturity classification;
- compatible contract/runtime/tool versions;
- release notes and known limitations;
- build/package provenance and SBOM when supported by the release workflow;
- deployment/install instructions;
- migration and rollback guidance;
- security/support implications.

A coordinated CoreLink stack release additionally includes a machine-readable component manifest and verifies that every promoted component artifact exists at the recorded exact version.

## Breaking changes

Breaking public-contract changes require an explicit major-version/migration decision. Consumer releases must not silently drift from normative contracts.

## Pre-release channels

Alpha/Beta/RC artifacts must be labeled as prerelease and must not be described as Stable. Scaffold repositories must not publish installation instructions that imply a supported artifact exists.

## GitHub Actions budget

CI should provide evidence with the least duplicated compute that preserves release confidence.

- Pull requests run fast quality/unit/contract checks appropriate to the changed paths.
- Expensive multi-platform container builds, SBOM/provenance generation, release image scans and end-to-end stack checks run at release time unless a change specifically requires them earlier.
- Successful pull-request checks should not be duplicated on `main` without a release/acceptance reason.
- Scheduled security/dependency checks should be grouped and throttled where practical; dependency update automation should prefer grouped minor/patch updates over many independent pull requests.
- Re-running a successful workflow solely to refresh evidence is discouraged; retain exact-SHA evidence instead.

## Product acceptance

Engineering completion, CI success, deployment success, and Product Acceptance are distinct. Product milestone acceptance remains owned by `product-planning` and must be backed by retained evidence appropriate to that milestone.

## Cross-repository reconciliation

A release or maturity change should update affected compatibility matrices, developer docs, repository README/status text, organization maturity/profile, and website claims in the same change set or link explicit follow-up work.
