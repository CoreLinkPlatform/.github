# Contributing to CoreLink Platform

Thank you for contributing to CoreLink Platform. CoreLink is managed as one product with multiple implementation and release boundaries.

## Before contributing

1. Search existing issues and pull requests.
2. Confirm that the change belongs in the selected repository.
3. For material product, architecture, security, or public-contract changes, link the relevant Product Epic or open a design issue first.
4. Do not expose private infrastructure, internal hostnames, customer information, credentials, or implementation-specific provider details in public surfaces.
5. Update documentation whenever behavior, compatibility, maturity, or supported operations change.

## Repository responsibilities

- `platform`: private CoreLink runtime and operational implementation.
- `Console`: hosted SaaS console. The capitalized name is an existing naming exception retained to avoid release/link churn.
- `api-contracts`: public/admin/internal API, event, webhook, and schema contracts.
- `developer-docs`: tutorials, guides, concepts, reference, and developer operations documentation.
- `sdk-typescript`: TypeScript client.
- `sdk-python`: Python client.
- `sdk-java`: future Java/Spring client; currently Scaffold.
- `cli`: future developer/operator CLI; currently Scaffold.
- `mcp-server`: future MCP integration boundary; currently Scaffold.
- `mock-server`: future contract-driven local/CI simulation; currently Scaffold.
- `website`: public product website and developer discovery surface.
- `product-planning`: product hierarchy, cross-repository Epics, milestone gates, risks, and acceptance decisions.
- `.github`: organization governance, community health, maturity, contribution, security, and shared templates.

The archived `demo-repository` is not an active product boundary. There is currently no standalone `examples` repository; runnable examples belong in the repository that owns them or in `developer-docs` until an examples repository is deliberately created.

## Public terminology

Public interfaces must be capability-oriented and implementation-independent. Prefer CoreLink-owned concepts such as Device Registry, Device Gateway, Telemetry Pipeline, Command Gateway, Provisioning Engine, Integration Adapter, and Identity Provider.

Do not expose provider-specific models, credentials, identifiers, package names, error codes, or payload fields as CoreLink public contracts.

## API and schema changes

Public-contract changes must:

- preserve stable operation identifiers where compatibility requires it;
- include request/response examples;
- define error responses and auth requirements;
- document compatibility impact;
- update the changelog/version metadata;
- pass contract linting and breaking-change checks;
- reconcile affected SDKs, docs, Console behavior, mock/MCP/CLI consumers, and release notes.

Breaking changes require an approved versioning and migration decision.

## Pull requests

Pull requests should address one logical change, include tests where applicable, update documentation, avoid unrelated formatting churn, identify compatibility/security implications, and link the owning Issue/Epic when one exists.

## Commit style

Use concise imperative Conventional Commit-style messages where practical:

```text
feat: add device command schema
fix: preserve request identifier in errors
docs: document client credentials flow
chore: update contract validation workflow
```

## Maturity and support claims

Use the organization maturity vocabulary: **Scaffold, Experimental, Alpha, Beta, Stable, Deprecated, Planned**. A merged feature, generated package, public repository, or release tag does not by itself establish Stable support. Check `REPOSITORY_MATURITY.md` and the owning repository's release evidence.

## Security

Security vulnerabilities must follow `SECURITY.md` and must not be disclosed in public issues or pull requests.

## License

By contributing, you agree that contributions are governed by the license declared by the target repository. Public visibility does not imply an open-source license.