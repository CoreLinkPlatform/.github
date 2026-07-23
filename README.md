# CoreLink GitHub Community Health

Repository-wide community-health and contribution assets for CoreLink
repositories.

## Contents

- `CONTRIBUTING.md`: contribution expectations.
- `CODE_OF_CONDUCT.md`: community behavior policy.
- `SECURITY.md`: vulnerability-reporting policy.
- `GOVERNANCE.md`: project governance.
- `ISSUE_TEMPLATE/`: bug, feature and documentation issue forms.
- `PULL_REQUEST_TEMPLATE.md`: pull-request checklist.
- `profile/README.md`: organization profile shown on GitHub.

## Usage

GitHub applies these files automatically only when this repository is named
`.github` at the organization level. If it is intentionally named `github` in
local development, copy or sync the reviewed files to the organization's
special `.github` repository before relying on GitHub to display or enforce
them.

Platform changes must also follow the architecture rules in the `platform`
repository, including tenant isolation, upstream-adapter boundaries, audit and
documentation review.
