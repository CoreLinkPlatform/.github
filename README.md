# CoreLink GitHub Community Health

Repository-wide community-health and contribution assets for CoreLink
repositories.

## Contents

- `CONTRIBUTING.md`: contribution expectations.
- `CODE_OF_CONDUCT.md`: community behavior policy.
- `SECURITY.md`: vulnerability-reporting policy.
- `GOVERNANCE.md`: project governance.
- `ISSUE_TEMPLATE/`: organization-wide bug, feature, implementation, Product Epic and documentation forms.
- `PULL_REQUEST_TEMPLATE.md`: pull-request checklist.
- `profile/README.md`: organization profile shown on GitHub.

## Usage

GitHub applies these files automatically only when this repository is named
`.github` at the organization level. If it is intentionally named `github` in
local development, copy or sync the reviewed files to the organization's
special `.github` repository before relying on GitHub to display or enforce
them.

Product Epics are owned by `product-planning`; executable Features/Tasks stay in the repository that implements them and link to exactly one primary Product Epic. Repository-local templates may narrow these defaults but must preserve that hierarchy.\n\nPlatform changes must also follow the architecture rules in the `platform`
repository, including tenant isolation, upstream-adapter boundaries, audit and
documentation review.
