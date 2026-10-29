---
name: normes
description: Normes partagées par Pierre (lemmatisation), Jacques (POS tagging) et Paul (vérification).
---

# Normes d'annotation - EACL2026

Utilisé par les agents définis dans `.vibe/agents/`.

## Ressources

- `data/corpus/*.tsv` : corpus à 4 colonnes (`text_form`, `form`, `lemma`, `pos`).
- `data/tagsets/*_tagset.txt` : étiquettes autorisées pour GRC, HYE, KAT et SYC.
- `data/prompt-templates/*` : modèles de prompts.

## Règles

### Pierre — Lemmatisation

- Attribuer un lemme par forme.
- Respecter le contexte et les conventions linguistiques.
- Ramener les formes fléchies au nominatif singulier, conformément aux consignes du projet.
- Signaler les ambiguïtés.

### Jacques — POS tagging

- Utiliser uniquement les étiquettes du tagset de la langue.
- Vérifier la cohérence entre le lemme et la catégorie grammaticale.
- Pour les formes combinées, respecter le format `token lemma1@lemme2 POS1@POS2`.

### Paul — Vérification

- Vérifier les lemmes et les étiquettes POS selon les conventions du projet.
- Vérifier la cohérence entre les lemmes et les étiquettes.
- Signaler les anomalies et les incertitudes.

## Contraintes

- Ne jamais modifier les fichiers de `data/corpus/`.
- Ne jamais inventer de lemme ou d'étiquette.
- Ne jamais coder de clé API en dur.
- Toujours signaler les incertitudes.

## Format

```text
text_form    form    lemma    pos
```

## Sortie attendue

| Agent   | Tâche         | Sortie              |
| ------- | ------------- | ------------------- |
| Pierre  | Lemmatisation | `lemma`             |
| Jacques | POS tagging   | `pos`               |
| Paul    | Vérification  | Rapport d'anomalies |
