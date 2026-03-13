# 🏦 Analyse du Risque de Crédit — German Credit Dataset

![ML](https://img.shields.io/badge/ML-Scikit--learn-orange.svg)
![Data Science](https://img.shields.io/badge/Data%20Science-Credit%20Default%20Risk-red.svg)
![Python](https://img.shields.io/badge/Python-3.8+-blue?logo=python)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange?logo=jupyter)

![Scikit-learn](https://img.shields.io/badge/Scikit--learn-1.2%2B-orange?logo=scikit-learn&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-1.5%2B-150458?logo=pandas&logoColor=white)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)
![License](https://img.shields.io/badge/License-MIT-lightgrey)


> **Analyse exploratoire et modèle de credit scoring sur 1000 clients allemands.**  
> L'objectif est d'identifier les clients à risque de défaut de crédit à partir de leurs caractéristiques socio-économiques.

---

## 📋 Table des matières

- [Contexte](#contexte)
- [Dataset](#dataset)
- [Structure du projet](#structure-du-projet)
- [Méthodologie](#méthodologie)
- [Principaux Résultats](#Principaux-Résultats)
- [Packages](#Packages)

---

## 🎯 Contexte

Le **risque de crédit** est au cœur de l'activité bancaire. Prédire si un client va rembourser son crédit ou faire défaut permet aux institutions financières de :

- Prendre des décisions d'octroi plus éclairées
- Réduire les pertes liées aux impayés
- Optimiser leur portefeuille de crédit

Ce projet analyse le célèbre **German Credit Dataset** et construit un modèle de **credit scoring** basé sur des algorithmes de machine learning.

---

## 📊 Dataset

**Source :** [German Credit Data](https://www.kaggle.com/datasets/uciml/german-credit)
 
| Caractéristique | Valeur |
|---|---|
| Nombre d'observations | 1 000 clients |
| Nombre de variables | 9 |
| Variable cible | `Default` (Good / Bad) |
| Valeurs manquantes | Supprimées |

### Variables du dataset

| Variable | Type | Description |
|---|---|---|
| `Age` | Numérique | Âge du client (19–75 ans) |
| `Sex` | Catégorielle | Genre (male / female) |
| `Job` | Catégorielle | Niveau de qualification |
| `Housing` | Catégorielle | Statut de logement (own / rent / free) |
| `Saving accounts` | Catégorielle | Niveau d'épargne |
| `Checking account` | Catégorielle | Solde du compte courant |
| `Credit amount` | Numérique | Montant du crédit (250–18 424 €) |
| `Duration` | Numérique | Durée du crédit en mois (4–72) |
| `Purpose` | Catégorielle | Objet du crédit |

---

## 📁 Structure du projet

```
credit-scoring-germany/
│
├── README.md
├── requirements.txt
├── .gitignore
│
├── notebooks/
│   └── credit_scoring.ipynb       # Analyse complète
│
├── data/
│   └── german_credit_data.csv     # Dataset source
│
└── images/                        # Visualisations exportées
    ├── distributions.png
    ├── correlation_matrix.png
    └── confusion_matrix.png
```

---

## 🔬 Méthodologie

### 1. Analyse Exploratoire des données (EDA)
- Distribution des variables numériques (Age, Credit Amount, Duration)
- Analyse des variables catégorielles (Sex, Job, Housing, etc.)
- Matrice de corrélation
- Détection et traitement des valeurs atypiques

### 2. Ingénierie des variables (Feature Engineering)
- Transformation logarithmique de `Credit amount` → `log_credit` (pour corriger l'asymétrie)
- Création de `Age²` pour capturer les effets non-linéaires de l'âge
- Encodage des variables catégorielles (Label Encoding / One-Hot)

### 3. Modèle de Credit Scoring
- Création de la variable cible `Default` (1 = Good, 2 = Bad)
- Séparation train/test
- Entraînement du modèle de classification
- Évaluation : Accuracy, ROC-AUC, Matrice de confusion

### 4. Interprétation Économique
> ⚠️ **Note importante** : Prédire "Good" pour un client "Bad" est bien plus coûteux pour l'institution que l'inverse. Le modèle est calibré pour minimiser ce type d'erreur.

---

## 📈 Principaux Résultats

### Statistiques descriptives

| Variable | Moyenne | Écart-type | Min | Max |
|---|---|---|---|---|
| Age | 35.5 ans | 11.4 | 19 | 75 |
| Credit amount | 3 271 € | 2 823 € | 250 € | 18 424 € |
| Duration | 20.9 mois | 12.1 | 4 | 72 |

### Profil des clients
- **69%** sont des hommes
- **63%** sont des travailleurs qualifiés (*skilled*)
- **71.3%** sont propriétaires de leur logement
- **33.7%** des crédits sont pour l'achat d'une voiture

### Performance du modèle

- **Accuracy :** XX%
- **ROC-AUC :** 0,63
- **Recall (classe Bad) :** XX%


---

## 🛠️ Packages

| Librairie | Usage |
|---|---|
| `pandas` | Manipulation des données |
| `numpy` | Calculs numériques |
| `matplotlib` / `seaborn` | Visualisations |
| `scikit-learn` | Modélisation et évaluation |
| `jupyter` | Environnement d'analyse |

---

## 👤 Auteur

**[kétia HABONIMANA]**  
Etudiante en Master 2 Ingénierie des Données et Evaluations Econométriques  
📧 ketiajoyeusehabonimana@gmail.com  
🔗 [ketia Hb](https://www.linkedin.com/in/kétia-hb-4932203b5) | [Mon Github](https://github.com/ketia-hb)

---

## 📄 Licence

Ce projet est sous licence MIT — voir le fichier [LICENSE](LICENSE) pour plus de détails.

---

*Dataset original : [UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/144/statlog+german+credit+data))*
Kaggle pour les données

---

*Projet personnel - 2026*
