# MLOps Lab 01 – Du notebook au mini-système production-ready

Ce projet illustre un **mini-système MLOps** complet, du notebook initial à une application prête pour la production locale.  
Il est basé sur un pipeline de prédiction du churn avec gestion de modèle versionné, API FastAPI, logs, monitoring et rollback.

---

## Structure du projet

```text
mlops-lab-01/
│
├─ data/
│   ├─ raw.csv              # Dataset brut (simulé)
│   └─ processed.csv        # Dataset nettoyé et validé
│
├─ logs/
│   └─ predictions.log      # Logs de prédiction (JSON)
│
├─ models/                  # Modèles entraînés (joblib)
│
├─ registry/
│   ├─ metadata.json        # Métadonnées des modèles
│   ├─ current_model.txt    # Modèle actuellement servi
│   └─ train_stats.json     # Statistiques d'entraînement (moyenne, std)
│
├─ src/
│   ├─ generate_data.py     # Génération de dataset brut
│   ├─ prepare_data.py      # Prétraitement et génération de processed.csv
│   ├─ train.py             # Entraînement, évaluation, enregistrement modèle
│   ├─ evaluate.py          # Évaluation complète + registre
│   ├─ api.py               # API FastAPI pour le serving
│   ├─ monitor_drift.py     # Détection de dérive sur les features
│   └─ rollback.py          # Gestion des versions et rollback de modèles
│
└─ README.md                # Ce fichier
