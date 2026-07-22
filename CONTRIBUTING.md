# Contributing to CoreLink Platform

Thank you for your interest in contributing to CoreLink Platform.

This document describes the contribution process shared by public repositories in the CoreLinkPlatform organization.

## Before contributing

Before opening a pull request:

1. Search existing issues and pull requests.
2. Confirm that the change belongs in the selected repository.
3. Open an issue before implementing major features or public API changes.
4. Avoid exposing private infrastructure, internal hostnames, customer information, credentials, or implementation-specific provider details.

## Repository responsibilities

- `api-contracts`: API, event, webhook, and schema contracts
- `developer-docs`: tutorials, guides, concepts, and API documentation
- `sdk-typescript`: TypeScript, Node.js, React, and Next.js SDKs
- `sdk-python`: Python SDK
- `sdk-java`: Java and Spring integrations
- `examples`: runnable integration examples
- `cli`: CoreLink command-line interface
- `mcp-server`: Model Context Protocol integrations
- `mock-server`: API simulation and local development

## Public terminology

Public interfaces must use capability-oriented and implementation-independent terminology.

Use terms such as:

- Device Registry
- Device Gateway
- Fleet Engine
- IoT Runtime
- Telemetry Pipeline
- Command Gateway
- Provisioning Engine
- Digital Twin Service
- Integration Adapter
- Identity Provider

Do not expose internal provider, vendor, product, infrastructure, or deployment names in:

- public APIs;
- schemas;
- SDK types;
- package names;
- examples;
- documentation;
- error codes;
- telemetry fields;
- MCP tools and resources.

## API and schema changes

Changes to public contracts must:

- preserve stable operation identifiers;
- include request and response examples;
- define error responses;
- document authentication and authorization requirements;
- include compatibility impact;
- update the changelog;
- pass contract linting and breaking-change checks.

Breaking changes require an approved proposal and a versioning plan.

## Pull requests

Pull requests should:

- address one logical change;
- include tests where applicable;
- update documentation;
- avoid unrelated formatting changes;
- use clear commit messages;
- include compatibility and security considerations.

## Commit style

Use concise imperative commit messages:

```text
feat: add device command schema
fix: preserve request identifier in errors
docs: document client credentials flow
chore: update contract validation workflow
```

## Development status

The project is under active development. APIs and SDKs may change until the first stable release.

## License

By contributing, you agree that your contributions will be licensed under the license declared by the target repository.