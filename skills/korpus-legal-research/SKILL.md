---
name: korpus-legal-research
description: European and Francophone legal, tax, case law, and Akoma Ntoso 3.0 / ELI statutory certification (FR, EU, LU, MC, AD) with SHA-256 & RFC 3161 proof.
---

# Korpus Legal — Official B2A MCP Connector (`v1.2.0`)

Use this skill whenever the task requires deterministic, cryptographically sealed (`SHA-256` + dual `RFC 3161`) outputs from **Korpus Legal** (`https://www.korpus.lu/api/v1/mcp`).

## Discovery & Protocol Support
- **Streamable HTTP Endpoint**: `https://www.korpus.lu/api/v1/mcp` (MCP `2024-11-05`, `2025-03-26`, `2025-06-18`, `2026-07-28`)
- **B2A Manifest & Live SLA Beacon**: `https://www.korpus.lu/.well-known/mcp.json`
- **Perplexity Connector Manifest**: `https://www.korpus.lu/.well-known/mcp-connector.json`
- **A2A Agent Card**: `https://www.korpus.lu/.well-known/agent-card.json`
- **OpenAPI 3.1.0 Specification**: `https://www.korpus.lu/openapi.json`
- **Probatory Proof Verifier (`0,00 EUR`)**: `https://www.korpus.lu/verify/<proof_id>`

## Primary `Output-First` Tools
- `probe_norm_validity_status`: Fast-lane point-in-time validity probe returning repeal/amendment status and SHA-256 seal.
- `certify_consolidated_statute_akoma`: Certifies consolidated statute text in Akoma Ntoso 3.0 XML + canonical ELI URI.
- `verify_jurisprudence_non_cassation`: Verifies case-law non-quashing status and citation authority (compliant with Art. L.111-13 COJ).
- `audit_legal_claim_groundedness`: Audits a legal or tax claim against primary sources with Pay-on-Verified-Hit >= 0.88.
- `synthesize_jurisdictional_rag_brief`: Synthesizes a 500-token grounded multi-jurisdiction legal brief with numbered SHA-256 citations.
- `resolve_doctrinal_taxonomy_authority`: Resolves doctrinal definitions, cross-border concepts, and authoritative commentary.
- `trace_normative_chronology_evolution`: Traces historical versions and applicability windows of a statutory provision.
- `subscribe_normative_drift_webhook`: Subscribes to signed JWS webhooks triggered upon statutory amendment or case-law reversal.
- `search`: Canonical hybrid statutory, case-law, BOFiP, and doctrinal search.
- `fetch`: Canonical deterministic retrieval of an article, ruling, or Akoma Ntoso node.

*(Legacy v1 tool names remain 100% supported on `tools/call` via transparent alias resolution.)*

## Authentication & Settlement Rails
1. **OAuth 2.1 + PKCE (`S256`) + DCR (RFC 7591 / RFC 9728 / RFC 8414)**: Mandatory for tenant-isolated RLS data.
2. **Public Catalogs & Stateless Simulators**: Support `HTTP 402` (`x402` EURC/USDC, Stripe MPP, and `AP2` JWS mandates) with `0,00 EUR` dry-run preflight where applicable.
