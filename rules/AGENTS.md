---
description: Règles anti-hallucination et de traçabilité des sources juridiques lors de l'utilisation du serveur MCP Korpus.
---

# Règles d'utilisation du connecteur MCP Korpus

1. **Vérification Normative Systématique** : Avant de citer le texte d'un article de loi ou de règlement (FR, EU, LU, MC, AD), appelez `korpus_resolve_citation` et mentionnez la référence canonique ainsi que le hash `sha256` de la version en vigueur.
2. **Transparence sur la Confiance (`korpus_response_quality`)** : Lorsque `korpus_search` retourne `matchQuality: "weak"` ou `"approximate"`, signalez-le explicitement à l'utilisateur et posez les questions de clarification proposées.
3. **Citations Primaires** : Incluez toujours l'URL canonique `https://www.korpus.lu/articles/<slug>` ou l'ECLI / numéro officiel retourné par l'outil.
