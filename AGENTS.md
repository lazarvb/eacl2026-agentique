# Instructions générales

## Pourquoi

Étudier l'utilisation des modèles de langage pour la lemmatisation et le POS tagging de l'arménien classique, du géorgien ancien, du grec ancien et du syriaque.

## Ressources

Trois agents sont définis dans `.vibe/agents/` :

| Agent   | Fichier        | Rôle                                                      |
| ------- | -------------- | --------------------------------------------------------- |
| Pierre  | `pierre.toml`  | Lemmatisation : produit `lemma`                           |
| Jacques | `jacques.toml` | POS tagging : produit `pos`                               |
| Paul    | `paul.toml`    | Vérification des annotations et signalement des anomalies |

**Fonctionnement :**

```text
Corpus d'entrée
    ├── Pierre → lemma
    ├── Jacques → pos
    └── Paul → vérification de lemma, pos et des tagsets
                  ↓
          Corpus annoté et validé
```

Pierre et Jacques travaillent en parallèle. Paul vérifie leurs résultats sans produire d'annotations. Aucun agent ne modifie les corpus originaux.

---

- `README.md` : présentation et utilisation du projet.
- `data/corpus/` : corpus d'entraînement et de test (TSV à 4 colonnes : `text_form`, `form`, `lemma`, `pos`).
- `data/prompt-templates/` : modèles de prompts.
- `data/tagsets/` : étiquettes grammaticales pour GRC, HYE, KAT et SYC.
- `scripts/` : scripts Python (`config.py`, `main.py`, `utils.py`).
- `pie-baseline/` : système de référence PIE.
- `results/` : résultats expérimentaux existants.
- `.vibe/agents/` : configurations TOML des trois agents.

Consulter les fichiers TOML pour connaître les consignes propres à chaque agent.

---

## Exemples d'utilisation

- **Lemmatisation :** utiliser Pierre.
- **POS tagging :** utiliser Jacques.
- **Validation :** utiliser Paul.
- **Annotation complète :** exécuter Pierre et Jacques en parallèle, puis Paul.

---

## Critères de réussite

Les modifications sont cohérentes, vérifiées, reproductibles et documentées. Les corpus, tagsets et résultats originaux restent intacts.

---

## Instructions générales

- Préserver les corpus, les fichiers de test et les résultats existants.
- Ne jamais exposer de clés API ou de secrets. Les agents n'ont pas accès aux clés API.
- Ne lancer aucune expérience coûteuse sans autorisation explicite.
- Limiter les modifications au besoin demandé.
- Effectuer les vérifications pertinentes et signaler les anomalies.

---

## Sortie attendue

Fournir un résumé des modifications effectuées, des vérifications réalisées et des anomalies détectées, en précisant les fichiers concernés. Signaler également les éventuels problèmes restants.
