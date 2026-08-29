# CoreLink Release Policy

CoreLink is one product with multiple release boundaries. Runtime, contracts, Console, SDKs, tools, documentation, and the website may have separate artifacts, but supported claims must reconcile through one product maturity model.

## Maturity

Use: **Scaffold, Experimental, Alpha, Beta, Stable, Deprecated, Planned**.

A tag or package publication does not by itself establish support. Supported releases require the owning repository's release gate plus compatible contract, security, documentation, and operational evidence.

## Version provenance

Released artifacts should identify immutable source and dependency revisions. Generated SDKs and contract consumers must identify the exact contract tag/revision used. Branch names are not release provenance.

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

## Breaking changes

Breaking public-contract changes require an explicit major-version/migration decision. Consumer releases must not silently drift from normative contracts.

## Pre-release channels

Alpha/Beta/RC artifacts must be labeled as prerelease and must not be described as Stable. Scaffold repositories must not publish installation instructions that imply a supported artifact exists.

## Product acceptance

Engineering completion, CI success, deployment success, and Product Acceptance are distinct. Product milestone acceptance remains owned by `product-planning` and must be backed by retained evidence appropriate to that milestone.

## Cross-repository reconciliation

A release or maturity change should update affected compatibility matrices, developer docs, repository README/status text, organization maturity/profile, and website claims in the same change set or link explicit follow-up work.