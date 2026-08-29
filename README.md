# CoreLink GitHub Community Health

Organization-wide governance and community-health assets for CoreLink repositories.

## Contents

- `CONTRIBUTING.md` — contribution expectations and repository responsibility map.
- `CODE_OF_CONDUCT.md` — community behavior and enforcement baseline.
- `SECURITY.md` — private vulnerability-reporting policy.
- `SUPPORT.md` — support routing and maturity expectations.
- `GOVERNANCE.md` — project decision model.
- `RELEASE_POLICY.md` — shared maturity, provenance, compatibility and release rules.
- `ISSUE_TEMPLATE/` — organization-wide issue forms.
- `PULL_REQUEST_TEMPLATE.md` — pull-request checklist.
- `profile/README.md` — organization profile shown on GitHub.
- `REPOSITORY_MATURITY.md` — reconciled active-repository roles and maturity claims.

## Source-of-truth boundaries

- Product hierarchy, Epics, milestone gates, risks and acceptance decisions: `product-planning`.
- Organization policy and maturity: `.github`.
- Machine-readable API/event contracts and compatibility: `api-contracts`.
- Human-facing developer guidance: `developer-docs`.
- Repository-specific implementation/deployment details: the owning repository.

Product Epics are owned by `product-planning`; executable Features/Tasks stay in the repository that implements them and link to a primary Product Epic. Repository-local templates may narrow these defaults but must preserve that hierarchy.

Platform changes must also follow architecture, tenant-isolation, adapter-boundary, audit and evidence rules documented by the `platform` repository.