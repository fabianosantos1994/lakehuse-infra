# 🏗️ Local Lakehouse Platform (V1)

## 📌 Overview

This project implements a local modern data platform based on a Lakehouse architecture.

It simulates a production-like environment using open-source technologies and follows the Medallion Architecture (Bronze, Silver, Gold).

## 🧠 Architecture

The platform is built with a clear separation of responsibilities:

* **MinIO** → Object Storage (S3-compatible)
* **Parquet** → File format
* **Apache Iceberg** → Table format
* **Hive Metastore** → Metadata catalog
* **PostgreSQL** → Backend for Hive Metastore and Airflow
* **Apache Spark** → Data processing engine
* **Apache Airflow** → Orchestration
* **Trino** → SQL query engine

### Compute Layer Separation

* **Spark** → ingestion and transformation
* **Trino** → query and analytics

## 🔄 Data Flow

```
Sources → Spark → Bronze → Silver → Gold → Trino → DBeaver
```

## 📦 Layers

* **Bronze** → raw ingestion
* **Silver** → cleaned and standardized data
* **Gold** → aggregated and business-ready datasets

## 🚀 Getting Started

### 1. Clone repository

```bash
git clone https://github.com/<your-user>/lakehouse-infra.git
cd lakehouse-infra/docker
```

### 2. Start infrastructure

```bash
docker compose up -d
```

### 3. Access services

* Airflow → http://localhost:8080
* Trino → http://localhost:8081
* MinIO → http://localhost:9001

## 🧪 Running Pipelines

Pipelines are orchestrated via Airflow.

Example DAGs:

* Bronze ingestion
* Silver transformation
* Gold aggregation

## 🔍 Querying Data

You can query data using:

* Trino CLI
* DBeaver

Example:

```sql
SELECT * FROM iceberg.gold.municipios_by_state;
```

## 📁 Repository Structure

```
docker/
trino/
airflow/
configs/
```

## 🎯 V1 Status

✅ Infrastructure ready
✅ Bronze pipeline
✅ Silver pipeline
✅ Gold pipeline
✅ Airflow orchestration
✅ Trino integration

## 🚀 Next Steps (V2)

* Dimensional modeling
* Data marts
* Business datasets
