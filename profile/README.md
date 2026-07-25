<div align="center">

# CoreLink Platform

### Connected product infrastructure for devices, applications, and digital services

Build, integrate, and operate connected products through consistent APIs, SDKs, event contracts, and developer tools.

[Developer Documentation](https://developers.corelinkplatform.ir)
·
[API Contracts](https://github.com/CoreLinkPlatform/api-contracts)
·
[Examples](https://github.com/CoreLinkPlatform/examples)
·
[Report an Issue](https://github.com/CoreLinkPlatform/developer-docs/issues)

</div>

---

## What is CoreLink?

CoreLink is a developer platform for integrating connected devices, applications, and business systems.

It provides a consistent abstraction over device communication, provisioning, telemetry, commands, digital twins, events, and external integrations.

CoreLink is designed for:

- connected-product manufacturers;
- IoT solution providers;
- fleet and mobility platforms;
- white-label applications;
- enterprise integration teams;
- backend, web, mobile, and automation developers.

## Platform capabilities

CoreLink provides common interfaces for:

- device registration and identity;
- device provisioning and lifecycle management;
- telemetry and state synchronization;
- remote command execution;
- location and mobility services;
- media and streaming workflows;
- event-driven integrations;
- webhooks and external system connectivity;
- multi-tenant and white-label applications;
- developer and AI-assisted integrations.

The public APIs describe platform capabilities rather than specific internal implementations. This allows the underlying infrastructure to evolve without forcing unnecessary changes on applications and integrations.

## Start here

| Resource | Description |
|---|---|
| [Developer documentation](https://github.com/CoreLinkPlatform/developer-docs) | Guides, concepts, tutorials, and API usage |
| [API contracts](https://github.com/CoreLinkPlatform/api-contracts) | OpenAPI, AsyncAPI, schemas, and Postman collections |
| [TypeScript SDK](https://github.com/CoreLinkPlatform/sdk-typescript) | SDK for Node.js, browsers, React, and Next.js |
| [Python SDK](https://github.com/CoreLinkPlatform/sdk-python) | SDK for Python applications and automation |
| [Java SDK](https://github.com/CoreLinkPlatform/sdk-java) | SDK for Java and Spring-based applications |
| [Examples](https://github.com/CoreLinkPlatform/examples) | Runnable integration examples |
| [CLI](https://github.com/CoreLinkPlatform/cli) | Command-line tools for developers and operators |
| [MCP Server](https://github.com/CoreLinkPlatform/mcp-server) | AI and agent integrations using Model Context Protocol |
| [Mock Server](https://github.com/CoreLinkPlatform/mock-server) | Local and CI-compatible API simulation |

## Quick example

```ts
import { CoreLink } from "@corelink/sdk";

const corelink = new CoreLink({
  baseUrl: process.env.CORELINK_API_URL!,
  accessToken: async () => process.env.CORELINK_ACCESS_TOKEN!,
});

const devices = await corelink.devices.list({
  tenantId: "tenant_id",
});

console.log(devices.items);
