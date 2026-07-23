# CoreLink MCP Server

The future Model Context Protocol server for AI-assisted, tenant-safe CoreLink
workflows.

## Current status

This repository is a scaffold. There is no server implementation, tool
manifest, authentication flow or distributable package yet.

## Intended tools

- Read tenant-scoped devices, lifecycle state, telemetry summaries and digital
  twins.
- Request and monitor approved commands.
- Search the public CoreLink contract and developer documentation.
- Perform narrowly scoped provisioning or integration actions only when the
  caller's CoreLink authorization permits them.

## Security requirements

- Authenticate users and services through CoreLink-supported flows; do not
  turn an upstream Keycloak, Traccar or OpenRemote token into a public bypass.
- Resolve tenant and authorization server-side for every tool call.
- Expose canonical CoreLink IDs and schemas, never raw provider credentials or
  internal integration identifiers.
- Make state-changing tools explicit, idempotent where appropriate and
  auditable.
- Derive tool input/output schemas from reviewed versioned contracts in
  `api-contracts`.
