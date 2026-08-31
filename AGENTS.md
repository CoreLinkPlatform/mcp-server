# CoreLink MCP Server Agent Context

This repository is part of the CoreLink product.

## Canonical context

Follow `CoreLinkPlatform/product-planning/AGENTS.md`, `PRODUCT_ARCHITECTURE.md`, `GLOSSARY.md`, `STANDARDS.md`, and `architecture/repository-map.yaml`. Public API behavior is normative in `CoreLinkPlatform/api-contracts`.

## Repository responsibility

`mcp-server` owns the supported MCP integration boundary that exposes approved CoreLink capabilities to compatible AI clients and agents.

## Boundaries

- Expose only supported, authorized CoreLink capabilities; MCP is not a bypass around product APIs or authorization.
- Never expose secrets, provider credentials, internal provider identifiers, or unrestricted cross-tenant data.
- Tool names, descriptions, schemas, and results must use canonical CoreLink terminology.
- Prefer deterministic read operations and narrowly scoped writes with explicit authorization and validation.
- Do not duplicate core business logic in the MCP layer.
- Any new capability that changes public product semantics must first be represented in the appropriate platform/API contract boundary.
