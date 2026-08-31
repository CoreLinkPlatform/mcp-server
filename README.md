# CoreLink MCP Server

[![Maturity: Scaffold / Planned](https://img.shields.io/badge/maturity-scaffold%20%2F%20planned-lightgrey)](https://github.com/CoreLinkPlatform/.github/blob/main/REPOSITORY_MATURITY.md)
[![Artifact: Not published](https://img.shields.io/badge/artifact-not%20published-lightgrey)](https://github.com/CoreLinkPlatform/mcp-server)
[![MCP: Planned](https://img.shields.io/badge/MCP-planned-blueviolet)](https://modelcontextprotocol.io/)
[![Contract: v1 draft](https://img.shields.io/badge/contract-v1%20draft-orange)](https://github.com/CoreLinkPlatform/api-contracts)

> **Maturity: Scaffold / Planned** — no supported MCP server package or tool manifest exists yet.

CoreLink MCP Server is the planned Model Context Protocol boundary for AI-assisted, tenant-safe CoreLink workflows. It must consume versioned public CoreLink contracts and preserve the same authorization/tenant boundaries as other clients.

## Current state

This repository currently contains documentation only. There is no server implementation, distributable package, authentication flow, or supported tool surface.

## Planned scope

### Read-only baseline

Subject to accepted MCP security and contract gates:

- discover public CoreLink contract/documentation revisions;
- read authorized tenant-scoped devices and lifecycle state;
- read supported telemetry/location summaries only when those public contracts are accepted;
- return canonical CoreLink IDs and maturity/version metadata.

### State-changing operations

State-changing tools are a separate Post-Beta/security-gated capability. They require a named product use case, explicit consent/confirmation semantics, least-privilege authorization, idempotency/recovery where applicable, and audit evidence. They are not required for the read-only MCP release candidate.

## Security boundary

Every supported tool must:

- resolve actor, tenant and authorization server-side;
- fail closed on insufficient scope and cross-tenant access;
- never turn provider/internal credentials into a public bypass;
- avoid exposing secrets or provider-specific IDs/payloads;
- use explicit consent for sensitive/mutating actions;
- emit audit evidence without leaking credentials;
- map inputs/outputs to version-identifiable CoreLink public contracts.

Prompt/tool instructions cannot grant privileges the caller does not already have.

## Backlog

- [MCP-01](https://github.com/CoreLinkPlatform/mcp-server/issues/2) — tenant/authorization/consent/audit threat model.
- [MCP-02](https://github.com/CoreLinkPlatform/mcp-server/issues/3) — read-only contract/docs/device/telemetry tools.
- [MCP-03](https://github.com/CoreLinkPlatform/mcp-server/issues/4) — separately gated state-changing tools.
- [MCP-04](https://github.com/CoreLinkPlatform/mcp-server/issues/5) — package/version/sandbox compatibility.

## Related sources

- [Developer docs](https://github.com/CoreLinkPlatform/developer-docs)
- [API contracts](https://github.com/CoreLinkPlatform/api-contracts)
- [Repository maturity](https://github.com/CoreLinkPlatform/.github/blob/main/REPOSITORY_MATURITY.md)

Installation/configuration examples will be published only after a real package and supported authentication/tool boundary exist.