# TaxiNYC# 🚖 NYC Taxi Lakehouse Data Pipeline on Azure

**Projet Data Engineering** basé sur les données publiques de la ville de New York (nyc.gov).  
Objectif : mettre en place un pipeline **automatisé**, **scalable** et **orienté analytique**,  
en appliquant la **Medallion Architecture** (Bronze / Silver / Gold).

---

## 🏗️ Architecture Globale

Le pipeline repose sur les services Cloud Azure et Databricks :

- **Source Data** : NYC Open Data (nyc.gov)
- **Orchestration & Traitement** : Azure Databricks (PySpark)
- **Stockage** : Azure Data Lake Storage (ADLS)
- **Modèle Médaillon** : Bronze → Silver → Gold (Delta Lake)
- **Visualisation** : Tableau (Dashboards)

📌 La collecte et l’ingestion des données sont **planifiées automatiquement chaque jour à 00h**.

---

## 🔁 Workflow (ETL / ELT)

### 1️⃣ Ingestion (Databricks Job)
- Téléchargement automatique des fichiers depuis nyc.gov
- Conversion en **Parquet**
- Stockage dans ADLS : `taxi_data/`


### 2️⃣ Bronze Layer
- Ingestion brute + création des tables Delta
- Contrôle de schéma & historisation
- Archivage des fichiers sources → `taxi_data/archive/`

### 3️⃣ Silver Layer
- Normalisation & nettoyage
- **Pipeline incrémental**
- Tables analytiques intermédiaires stockées dans `silver/`

### 4️⃣ Gold Layer
- Enrichissement métier
- Agrégations & KPIs
- Tables prêtes pour la BI stockées dans `gold/`

---

## 📊 Visualisation

Les données Gold alimentent un dashboard interactif créé avec **Tableau**  

👉 Lien du Dashboard : *(À ajouter ici lorsque publié)*

---

## 📁 Structure du projet
📦 nyc-taxi-lakehouse-azure
│
├── notebooks/
│ ├── 01_ingestion_nyc_data.py
│ ├── 02_bronze_pipeline.py
│ ├── 03_silver_pipeline.py
│ └── 04_gold_pipeline.py
│
├── architecture/
│ └── data_pipeline_final.png
│
├── dashboard/
│ └── screenshots/
│ 
│
│
└── README.md

---

## 🧰 Technologies utilisées

| Domaine | Outils |
|--------|--------|
| Cloud | Azure Data Lake Storage |
| Compute | Azure Databricks (Spark / Delta Lake) |
| Stockage | Parquet & Delta Lake |
| Orchestration | Databricks Jobs (Scheduling) |
| BI | Tableau |
| Langages | Python, PySpark |

---


## 📜 Licence

Projet réalisé à des fins pédagogiques dans le cadre de ma montée en compétences en Data Engineering.

---

✍️ Réalisé par **Louis-Carlos Francisco**  
📩 Contact LinkedIn : www.linkedin.com/in/louis-carlos-francisco-9025b0251
