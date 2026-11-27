# Korpus Legal — Official B2A & Enterprise MCP Connector (`v1.2.0`)

European and Francophone legal, tax, case law, and Akoma Ntoso 3.0 / ELI statutory certification (FR, EU, LU, MC, AD) with SHA-256 & RFC 3161 proof.

## Sovereign Endpoints & Discovery
| Surface | URL |
| :--- | :--- |
| **MCP Streamable HTTP** | `https://www.korpus.lu/api/v1/mcp` |
| **MCP Discovery & SLA Beacon** | `https://www.korpus.lu/.well-known/mcp.json` |
| **Perplexity Connector Manifest** | `https://www.korpus.lu/.well-known/mcp-connector.json` |
| **A2A Agent Card** | `https://www.korpus.lu/.well-known/agent-card.json` |
| **OAuth 2.1 Protected Resource (RFC 9728)** | `https://www.korpus.lu/.well-known/oauth-protected-resource` |
| **OAuth 2.1 Authorization Server (RFC 8414)** | `https://www.korpus.lu/.well-known/oauth-authorization-server` |
| **OpenAPI 3.1.0 Spec** | `https://www.korpus.lu/openapi.json` |
| **Agent Index (`llms.txt`)** | `https://www.korpus.lu/llms.txt` |

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

## Guarantees
- **Zero Data Retention (`ZDR`)**: `X-Data-Retention: zero`, `X-Training-On-Payloads: false`, EU sovereign processing (`EU-FR-LU`).
- **AST Prompt-Injection Defense**: 6-layer deterministic sanitizer (`X-Prompt-Injection-Sanitized: ast-v2`).
- **Cryptographic Opposability**: `SHA-256` payload digest + dual qualified `RFC 3161` timestamps + `0,00 EUR` counterparty verification at `https://www.korpus.lu/verify/<proof_id>`.
