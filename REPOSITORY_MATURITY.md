# CoreLink repository maturity inventory

**Last reconciled: 2026-08-06**

CoreLink is one product delivered through multiple repositories. This inventory
records repository role and maturity; it is not a second product roadmap.
Product goals, milestones and cross-repository Epics remain authoritative in
[`product-planning`](https://github.com/CoreLinkPlatform/product-planning).

Maturity words follow the shared CoreLink vocabulary: **Scaffold**,
**Experimental**, **Alpha**, **Beta**, **Stable**, **Deprecated**, and
**Planned**. Repository visibility or the presence of source code does not make
a capability Stable or commercially supported.

## Current inventory

| Repository | Product role | Current maturity | What that means now |
| --- | --- | --- | --- |
| [`platform`](https://github.com/CoreLinkPlatform/platform) | Core runtime | Implemented foundation / pre-release | Substantial tenancy, identity, device, command and event foundations exist; product acceptance gates are still open. |
| [`api-contracts`](https://github.com/CoreLinkPlatform/api-contracts) | Public/admin/internal API and event contracts | Alpha · `1.0.0-draft` public boundary | Device + Command public slice and canonical event envelope are reviewable; draft is not a Stable v1 release. |
| [`developer-docs`](https://github.com/CoreLinkPlatform/developer-docs) | Versioned developer documentation | Alpha | v1 information architecture and contract-backed quickstart target the draft public boundary. |
| [`sdk-typescript`](https://github.com/CoreLinkPlatform/sdk-typescript) | TypeScript client | Prerelease Alpha | Generated client exists; no production-supported package release is claimed. |
| [`sdk-python`](https://github.com/CoreLinkPlatform/sdk-python) | Python client | Prerelease Alpha | Generated client exists; no production-supported package release is claimed. |
| [`sdk-java`](https://github.com/CoreLinkPlatform/sdk-java) | Java client | Scaffold · Planned | No supported Java package exists yet. |
| [`cli`](https://github.com/CoreLinkPlatform/cli) | Developer/operator CLI | Scaffold · Planned | No installable supported CLI exists yet. |
| [`mock-server`](https://github.com/CoreLinkPlatform/mock-server) | Local/CI API simulation | Scaffold · Planned | No supported mock-server package/runtime exists yet. |
| [`mcp-server`](https://github.com/CoreLinkPlatform/mcp-server) | Agent/MCP integration | Scaffold · Planned | No supported MCP server/tool surface exists yet. |
| [`website`](https://github.com/CoreLinkPlatform/website) | Public product website | Active public surface / pre-release claims | Claims must mirror this inventory and retained repository/release evidence. |
| [`product-planning`](https://github.com/CoreLinkPlatform/product-planning) | Product governance | Source of truth | Owns product hierarchy, milestones, decisions and cross-repository acceptance. |
| [`.github`](https://github.com/CoreLinkPlatform/.github) | Organization governance/community health | Source of truth | Owns organization defaults, profile, contribution/security policy and shared Issue forms. |

The former `examples` link is intentionally absent: no accessible
`CoreLinkPlatform/examples` repository was found during this reconciliation.
Examples must not be advertised as a runnable product resource until a real,
versioned repository and acceptance evidence exist.

## Capability boundary represented publicly

Today the public developer boundary is intentionally narrower than the internal
runtime foundation:

- public API contract: Device + Command on `1.0.0-draft`;
- public event contract: canonical event envelope;
- TypeScript/Python clients: prerelease Alpha;
- Java/CLI/mock/MCP: Scaffold/Planned;
- telemetry, digital twin, media, white-label and broader integration claims
  require their own contract/runtime/release evidence before being presented as
  Stable supported public capability.

## Ownership and review

- Product Council/product planning owns milestone and product-maturity decisions.
- Each repository owns implementation evidence and its repository README.
- The website and organization profile may summarize maturity but must link back
  to the owning repository/contract instead of becoming independent roadmaps.
- A repository owner changing a public maturity claim must update affected docs,
  website/profile copy and retained release evidence in the same product change
  or link follow-up work explicitly.
- Exceptions are recorded as product decisions in `product-planning`; they are
  not hidden in marketing copy or repository-local status text.

## Reconciliation cadence

Review this inventory at every product milestone gate and whenever a repository
enters or leaves Scaffold/Experimental/Alpha/Beta/Stable/Deprecated status.
A release tag alone is insufficient: contract compatibility, runtime evidence,
documentation and the owning repository's acceptance gate must agree.
