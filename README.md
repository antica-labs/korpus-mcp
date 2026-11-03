# Korpus Legal Intelligence — Plugin Google Antigravity & MCP

Connectez **Korpus** (`https://www.korpus.lu`), le corpus juridique et fiscal scientifique sans hallucination (France, Union Européenne, Luxembourg, Monaco, Andorre), directement à votre agent IA.

## Installation & Création de Compte

1. **OAuth 2.1 automatique** : À la première requête, Antigravity (ou Claude / ChatGPT / Codex) ouvre la page sécurisée `https://www.korpus.lu/api/oauth/authorize`.
2. **Nouveau sur Korpus ?** Cliquez sur **Créer un compte Korpus** (`https://www.korpus.lu/auth/register`) pour ouvrir votre compte en quelques secondes.
3. **Clé API MCP** : Générez une clé `kpus_live_...` depuis **Paramètres → Clés API** (`https://www.korpus.lu/app/settings/api-keys`) et validez l'autorisation OAuth 2.1.

## Exemples de prompts

- *"Résous le texte exact en vigueur et le hash SHA-256 de l'article 14 de la Llei de l'impost sobre societats (AD) via korpus_resolve_citation."*
- *"Cherche la jurisprudence et la doctrine récentes sur la rupture brutale des relations commerciales établies en France."*
- *"Vérifie cette affirmation juridique avec korpus_verify_claim et donne-moi le score de groundedness."*
