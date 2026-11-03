---
name: korpus-legal-research
description: Recherche juridique, fiscale et réglementaire multi-juridictions (France, Union Européenne, Luxembourg, Monaco, Andorre) avec résolution exacte des textes en vigueur + SHA-256 anti-hallucination via le serveur MCP officiel de Korpus (korpus.lu).
---

# Korpus — Intelligence Juridique, Fiscale & Réglementaire (MCP)

Utilisez cette compétence pour toute question de droit, de fiscalité, de jurisprudence ou de réglementation couvrant la **France (`FR`)**, l'**Union Européenne (`EU`)**, le **Luxembourg (`LU`)**, **Monaco (`MC`)** et l'**Andorre (`AD`)** via **Korpus** (`https://www.korpus.lu`).

## Authentification & Création de Compte

Le serveur MCP Korpus (`https://www.korpus.lu/api/v1/mcp`) supporte :
1. **OAuth 2.1 + PKCE (`S256`)** via `https://www.korpus.lu/.well-known/oauth-authorization-server` : ouvre automatiquement la fenêtre d'autorisation et de création de compte (`https://www.korpus.lu/auth/register`).
2. **Bearer Token (`kpus_live_...`)** généré depuis **Paramètres → Clés API** (`https://www.korpus.lu/app/settings/api-keys`).

## Règle d'Or Anti-Hallucination

1. **Ne citez jamais un article de loi de mémoire** : appelez systématiquement `korpus_resolve_citation` (`textRef`, `articleNumber`, `country`, `atDate`) pour obtenir le texte exact en vigueur et son empreinte `sha256`.
2. **Respectez le bloc `korpus_response_quality`** retourné par `korpus_search` :
   - Si `matchQuality` vaut `approximate` ou `weak`, ne présentez pas le résultat comme certain et posez les questions listées dans `clarifications`.

## Les 13 Outils MCP Korpus (`readOnlyHint: true`)

- `korpus_resolve_citation` : Texte intégral en vigueur d'un article de loi/règlement + `sha256` + support time-travel (`atDate`).
- `korpus_search` (et alias `search`) : Recherche hybride RRF (lexicale BM25 + vectorielle `voyage-law-2`) filtrable par `jurisdictions` (`FR`, `EU`, `LU`, `MC`, `AD`) et `categories` (`loi`, `reglement`, `rescrit_fiscal`, `jurisprudence`, `doctrine`, `constitution`, `convention`).
- `korpus_get_article` (et alias `fetch`) : Lecture complète d'un article ou commentaire (headnotes, concepts, groundedness score, hash SHA-256).
- `korpus_rag_query` : Synthèse juridique RAG sourcée avec notes de bas de page vérifiées.
- `korpus_verify_claim` : Vérification factuelle d'une affirmation juridique avec score de groundedness `0..1`.
- `korpus_get_decision` : Décision judiciaire brute par numéro de pourvoi ou ECLI.
- `korpus_get_concept` : Concept taxonomique EuroVoc / LKIF / Korpus et articles rattachés.
- `korpus_get_relations` : Graphe de citations jurisprudentielles (`cite`, `casse`, `confirme`, `distingue`, `abroge`, `contredit`).
- `korpus_explain_legal_term` : Définition taxonomique + doctrine + arrêts de référence.
- `korpus_list_authorities` : Score d'autorité scientifique des auteurs cités (h-index OpenAlex, tier Platinum/Gold/Silver/Bronze, ORCID).
- `korpus_get_chronology` : Évolution chronologique jurisprudentielle et législative d'une notion.
