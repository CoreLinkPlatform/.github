# Security Policy

## Reporting a vulnerability

Do **not** report security vulnerabilities through public GitHub issues, discussions, pull requests, or comments.

Use GitHub's private vulnerability reporting / Security Advisory flow on the affected CoreLink repository when that private reporting option is available. If a repository does not expose a private reporting flow, contact a CoreLink maintainer through an existing private organizational channel and identify the affected repository so a private advisory can be opened.

Include, where possible:

- affected repository and version or commit;
- vulnerability description and security boundary affected;
- minimal reproduction steps;
- expected and actual behavior;
- potential impact;
- suggested mitigation, if known;
- sanitized logs or screenshots.

Do not include unnecessary secrets, access tokens, client secrets, private keys, customer data, production credentials, or personally identifiable information.

## Response process

We aim to:

- acknowledge a private report within 5 business days;
- investigate impact and affected versions;
- coordinate remediation and disclosure;
- publish a GitHub Security Advisory when appropriate;
- update supported release and mitigation guidance.

These targets are operational goals, not contractual service-level guarantees.

## Supported versions

Until the first Stable release, only the latest published preview release is evaluated for security updates unless a release note explicitly states otherwise. Stable-version support windows will be documented when Stable releases begin.

## Scope

Security reports may include:

- authentication or authorization bypass;
- tenant-isolation or RLS failures;
- credential or secret exposure;
- command-execution vulnerabilities;
- webhook signature or replay-control bypass;
- request forgery or unsafe callback behavior;
- unsafe SDK/CLI credential handling;
- dependency vulnerabilities with demonstrated product impact;
- MCP authorization, consent, or data-exposure failures;
- release/supply-chain provenance weaknesses with exploitable impact.

General support requests, implementation questions, and feature requests should use the appropriate repository issue tracker or `SUPPORT.md`.