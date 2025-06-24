# fraud-detection-bigdata
# README - Fraud Detection Big Data Project

## 📌 Objectif du projet
Concevoir et déployer une architecture Big Data complète pour la **détection de fraudes bancaires** à partir de données simulées et enrichies. L’architecture combine plusieurs bases de données (SQL/NoSQL), du streaming Kafka, du traitement Spark, une API FastAPI et du monitoring Prometheus + Grafana.

---

## 🗂️ Stack Technologique

| Composant         | Rôle                                                                 |
|------------------|----------------------------------------------------------------------|
| PostgreSQL       | Stockage relationnel des données client, carte, transaction         |
| MongoDB          | Stockage semi-structuré des profils enrichis                        |
| Cassandra        | Transactions critiques (fraudes) à haute disponibilité              |
| Redis            | Cache mémoire des soldes les plus récents                          |
| Neo4j            | Analyse des graphes relationnels (clients-cartes-transactions)      |
| Kafka            | Streaming des transactions en temps réel                            |
| HDFS             | Stockage distribué pour gros volumes de fichiers                    |
| Spark            | Traitement analytique et détection de fraudes                      |
| FastAPI          | API RESTful exposant les données                                    |
| Prometheus       | Collecte des métriques                                               |
| Grafana          | Visualisation et alertes sur les métriques                         |
| Docker           | Containerisation de l’ensemble du projet                           |

---

## 📁 Structure du projet

```
fraud_detection_project/
│
├── data/                      # Données CSV (transactions, clients...)
│
├── docker/                   # Dockerfiles + docker-compose.yml
│
├── api/                      # API FastAPI
│   ├── main.py
│   ├── models/
│   ├── routes/
│   └── utils/
│
├── consumers/                # Kafka consumers (Redis, Cassandra...)
│
├── producers/                # Kafka producer
│
├── spark/                    # Scripts Spark de traitement
│
├── neo4j/                    # Import des données dans Neo4j
│
├── hdfs/                     # Scripts HDFS
│
├── prometheus_grafana/       # Configs monitoring
│
├── .env                      # Variables d’environnement
├── setup.sh                  # Script de démarrage automatisé
├── README.md
├── requirements.txt
└── docker-compose.yml
```

---

## 🔄 Pipeline de données

1. **Simulation des données** : `generate_transactions.py`, `generate_clients.py`
2. **Enrichissement CSV (Kaggle)**
3. **Stockage initial** : PostgreSQL + MongoDB
4. **Streaming Kafka** : topic `banksim_topic`
5. **Traitement Spark** : détection de fraudes en flux
6. **Stockage critique** : Cassandra, Redis, HDFS
7. **Analyse de graphe** : Neo4j
8. **API REST** : FastAPI + JWT
9. **Monitoring** : Prometheus + Grafana

---

## 🚀 Démarrage rapide

### 1. Cloner le projet
```bash
git clone https://github.com/tonuser/fraud-detection-bigdata.git
cd fraud-detection-bigdata
```

### 2. Lancer toute l’infra avec Docker
```bash
chmod +x setup.sh
./setup.sh
```

### 3. Accéder aux services
| Service     | URL                                  |
|-------------|---------------------------------------|
| API         | http://localhost:8000/docs            |
| Kafka UI    | http://localhost:9000                 |
| Grafana     | http://localhost:3000 (admin/admin)   |
| Prometheus  | http://localhost:9090                 |
| Neo4j       | http://localhost:7474 (neo4j/password)|

---

## 📊 Dashboards
- **Grafana** : métriques Spark, API, Kafka, Redis...
- **Neo4j** : graphe client-transaction
- **FastAPI Swagger** : documentation interactive

---

## 🤝 Contributions
Ce projet a été réalisé dans le cadre d’un bloc de compétences Data/Big Data :
> "Concevoir et développer une architecture de stockage et traitement de données massives orientée détection de fraudes."

---

## 🧠 Auteurs

