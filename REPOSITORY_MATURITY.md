# CoreLink repository maturity inventory

**Last reconciled: 2026-08-30**

CoreLink is one product delivered through multiple repositories. This inventory records repository role and maturity; it is not a second product roadmap. Product goals, milestones, cross-repository Epics, and acceptance decisions remain authoritative in [`product-planning`](https://github.com/CoreLinkPlatform/product-planning).

Maturity vocabulary: **Scaffold, Experimental, Alpha, Beta, Stable, Deprecated, Planned**. Repository visibility, source-code volume, a merged PR, or a release tag does not by itself establish Stable/commercial support.

## Active repository inventory

| Repository | Product role | Current maturity | Current meaning |
| --- | --- | --- | --- |
| [`platform`](https://github.com/CoreLinkPlatform/platform) | Core runtime | Alpha / implemented foundation | Substantial tenancy, identity, device, command, telemetry/event, commercial and operational foundations exist; hosted-alpha and product acceptance gates remain active. |
| [`Console`](https://github.com/CoreLinkPlatform/Console) | Hosted tenant/customer SaaS console | Alpha | Deployable tenant-facing Console exists with OIDC/BFF and operational journeys. Provider implementation details are not part of its product contract. |
| [`Control`](https://github.com/CoreLinkPlatform/Control) | Private platform control plane / operator UI | Alpha | Internal privileged operations surface for platform overview, tenants, devices, managed connections and diagnostics. It is not a tenant/customer portal and must remain fail-closed to non-platform actors. |
| [`api-contracts`](https://github.com/CoreLinkPlatform/api-contracts) | Public/admin/internal API and event contracts | Alpha · `1.0.0-draft` public boundary | Device + Command public slice and canonical event envelope are reviewable; broader v1 contract work is ongoing. |
| [`developer-docs`](https://github.com/CoreLinkPlatform/developer-docs) | Versioned developer documentation | Alpha | Versioned v1 IA exists; quickstart and broader guides are being reconciled with supported contract/runtime maturity. |
| [`sdk-typescript`](https://github.com/CoreLinkPlatform/sdk-typescript) | TypeScript client | Prerelease Alpha | Generated client exists; supported publication/conformance gates are still open. |
| [`sdk-python`](https://github.com/CoreLinkPlatform/sdk-python) | Python client | Prerelease Alpha | Generated client exists; supported publication/conformance and license-policy gates are still open. |
| [`sdk-java`](https://github.com/CoreLinkPlatform/sdk-java) | Java client | Scaffold · Planned | No supported Java source/package/build baseline exists yet. |
| [`cli`](https://github.com/CoreLinkPlatform/cli) | Developer/operator CLI | Scaffold · Planned | No installable supported CLI exists yet. |
| [`mock-server`](https://github.com/CoreLinkPlatform/mock-server) | Local/CI contract simulation | Scaffold · Planned | No supported mock runtime/package exists yet; it must consume reviewed versioned contracts. |
| [`mcp-server`](https://github.com/CoreLinkPlatform/mcp-server) | Agent/MCP integration | Scaffold · Planned | No supported MCP package/tool surface exists yet; security and read-only boundaries are backlog-gated. |
| [`website`](https://github.com/CoreLinkPlatform/website) | Public product website | Active public surface / Alpha claims | GitHub Pages is the supported production path; public claims must mirror this inventory and retained evidence. |
| [`product-planning`](https://github.com/CoreLinkPlatform/product-planning) | Product governance | Source of truth | Owns product hierarchy, milestone gates, risks, cross-repository Epics and acceptance decisions. |
| [`.github`](https://github.com/CoreLinkPlatform/.github) | Organization governance/community health | Source of truth | Owns organization profile, maturity, contribution/security/support/release policy and shared templates. |

**Active repositories: 14.** The archived `demo-repository` is excluded from active-product coverage.

`Console` and `Control` are documented capitalized naming exceptions retained to avoid breaking existing links, release automation and deployment references. New repositories should continue to use lowercase kebab-case.

There is currently no standalone `CoreLinkPlatform/examples` repository. Runnable examples must not be advertised as a separate repository until one is deliberately created, versioned, and accepted.

## Product-surface boundary

- **Console** is the canonical tenant/customer/partner/reseller product surface.
- **Control** is a separate private privileged platform-operator surface. Tenant roles do not imply Control access.
- Provider identities, raw provider payloads and infrastructure diagnostics may appear in Control when operationally necessary, but remain implementation details and must not become tenant-facing public contracts.

## Public capability boundary

The public developer boundary remains intentionally narrower than the private runtime foundation:

- public API contract: Device + Command on `1.0.0-draft`;
- public event contract: canonical event envelope;
- TypeScript/Python clients: prerelease Alpha;
- Console: Alpha hosted application;
- Control: private Alpha operator surface and not a public developer API contract;
- Java/CLI/mock/MCP: Scaffold/Planned;
- telemetry/location, partner operations, usage/billing, automation/media and other surfaces require version-identifiable contract/runtime/release evidence before Stable support claims.

## Ownership and review

- Product planning owns milestone and product-maturity decisions.
- Each implementation repository owns implementation evidence, local development/deployment documentation, and its repository README.
- `Control` requires explicit platform-operator ownership/security review because it aggregates cross-tenant and provider/infrastructure diagnostics.
- `api-contracts` owns normative machine-readable API/event schemas and compatibility policy.
- `developer-docs` owns human-facing tutorials, concepts, guides, examples, and developer troubleshooting.
- `website` and the organization profile summarize maturity but must link to authoritative sources rather than becoming independent roadmaps.
- A maturity change must reconcile affected docs, website/profile copy, package metadata, compatibility matrices, stack manifests and release evidence.
- Exceptions are explicit product/governance decisions, not hidden marketing or repository-local wording.

## Reconciliation cadence

Review this inventory at every product milestone gate and whenever a repository enters or leaves Scaffold/Experimental/Alpha/Beta/Stable/Deprecated status, or when an active repository is created/archived. Contract compatibility, runtime evidence, documentation, and owning-repository acceptance must agree.