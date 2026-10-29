# Instructions pour les scripts

## Pourquoi

Maintenir un code Python fiable et reproductible pour orchestrer les agents Pierre, Jacques et Paul.

## Ressources

Les scripts `config.py`, `main.py` et `utils.py` permettent de configurer les tâches, d'exécuter les annotations et de valider les résultats.

```text
config.py → main.py → Appels API LLM
                       ├── Pierre : lemmatisation
                       ├── Jacques : POS tagging
                       └── Paul : validation des résultats
```

---

- `config.py` : configuration des tâches, modèles et chemins.
- `main.py` : exécution des annotations.
- `utils.py` : fonctions communes, lecture TSV et appels API.
- `requirements.txt` : dépendances Python.

---

## Exemples

- **Ajouter une tâche :** configurer les prompts et corpus dans `config.py`.
- **Tester une annotation :** exécuter `python main.py` avec une configuration adaptée.
- **Valider les résultats :** utiliser Paul pour vérifier les sorties de Pierre et Jacques.

---

## Critères de réussite

Les annotations sont reproductibles et les résultats validés par Paul avant acceptation.

---

## Instructions

- Respecter les dépendances définies dans `requirements.txt`.
- Ne jamais coder de clé API en dur. Utiliser des variables d'environnement ou un fichier `.env` exclu de Git.
- Ne pas lancer d'expérience coûteuse sans autorisation explicite, notamment avec les modèles payants.
- Ne pas modifier les résultats existants dans `results/` sans autorisation.
- Privilégier les changements ciblés et documentés.

---

## Sortie attendue

Résumer les fichiers modifiés, le comportement attendu, les tests effectués et les problèmes restants.

---
