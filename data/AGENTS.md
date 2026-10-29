# Instructions pour les données

## Pourquoi

Garantir l’intégrité et la cohérence des données utilisées pour la lemmatisation (Pierre) et le POS tagging (Jacques).

## Ressources

Les données sont utilisées par les 3 agents définis dans `.vibe/agents/`.

| Agent   | Données utilisées       | Sortie produite       | Fichiers concernés                |
| ------- | ----------------------- | --------------------- | --------------------------------- |
| Pierre  | `form` (colonne 2)      | `lemma` (colonne 3)   | `corpus/train/`, `corpus/test_*/` |
| Jacques | `form` (colonne 2)      | `pos` (colonne 4)     | `tagsets/*_tagset.txt`            |
| Paul    | `lemma`, `pos`, tagsets | Rapport de validation | Tous les fichiers concernés       |

**Format des données :** tous les fichiers TSV doivent contenir 4 colonnes :

```text
text_form    form    lemma    pos
```

---

- `corpus/train/` : données d’entraînement (4 700 mots par langue).
- `corpus/test_in-domain/` : tests in-domain (300 mots).
- `corpus/test_out-of-domain/` : tests out-of-domain (300 mots).
- `prompt-templates/` : modèles de prompts pour Pierre et Jacques.
- `tagsets/` : étiquettes autorisées pour Jacques et Paul.

**Règles strictes :**

- Aucun agent ne doit modifier les fichiers originaux.
- Les tagsets définissent les seules étiquettes autorisées pour chaque langue.

---

## Exemples

- **Pierre :** lit `form` dans `GRC_test.tsv` (ex. `ιωαννου`) pour produire le lemme.
- **Jacques :** utilise `GRC_tagset.txt` pour sélectionner les étiquettes valides (ex. `N+Ant`, `PRO+Dem`).
- **Paul :** vérifie les annotations et leur conformité aux tagsets.

---

## Critères de réussite

Les données originales sont préservées et les annotations respectent les conventions propres à chaque langue.

---

## Instructions

- Ne jamais modifier, supprimer ou écraser les fichiers de `data/`.
- Respecter la séparation entre `train/`, `test_in-domain/` et `test_out-of-domain/`.
- Ne pas supposer que les formats et étiquettes sont identiques entre GRC, HYE, KAT et SYC.
- Vérifier la présence des 4 colonnes TSV avant utilisation.

---

## Sortie attendue

Fournir un bilan des vérifications, les anomalies détectées et les fichiers concernés.

---
