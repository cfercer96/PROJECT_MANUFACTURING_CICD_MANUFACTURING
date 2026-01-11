🏭 Manufacturing Analytics ETL Pipeline

Arquitectura Medallion en Azure Databricks

Azure Databricks · PySpark · Delta Lake · Unity Catalog · Power BI · CI/CD

Pipeline automatizado de datos para análisis de procesos productivos y defectos de manufactura, implementado con arquitectura Bronze–Silver–Gold, gobierno de datos con Unity Catalog y consumo analítico en Power BI.

🎯 Descripción

Pipeline ETL enterprise-grade que procesa datasets de manufactura (producción híbrida y defectos), transformando datos crudos en datasets analíticos listos para BI.
El proyecto implementa la Arquitectura Medallion sobre Azure Databricks + Delta Lake, asegurando ACID, versionado, control de accesos y trazabilidad completa, con publicación final en Azure SQL / Power BI.

✨ Características Principales

🔄 ETL Automatizado – Pipelines orquestados con Databricks Workflows

🏗️ Arquitectura Medallion – Bronze → Silver → Gold

🧱 Delta Lake – ACID transactions, schema evolution, time travel

🔐 Unity Catalog – Gobierno de datos, permisos y aislamiento por capas

📊 Power BI Ready – Gold optimizado para visualización

🚀 CI/CD – Deploy automatizado desde GitHub

📈 KPIs de Manufactura – Métricas listas para análisis operativo

🔔 Monitoreo – Logs detallados y control de ejecuciones

🏛️ Arquitectura
Flujo de Datos
📄 CSV / Raw Data
      ↓
🥉 Bronze Layer (Ingesta sin transformación)
      ↓
🥈 Silver Layer (Limpieza + Normalización)
      ↓
🥇 Gold Layer (KPIs y métricas de negocio)
      ↓
🗄️ Azure SQL Database
      ↓
📊 Power BI Dashboards

📦 Capas del Pipeline
🥉 Bronze Layer

Propósito: Zona de aterrizaje (raw)

Tablas:

bronze_hybrid_manufacturing

bronze_manufacturing_defects

Características:

✅ Datos tal como vienen de origen

✅ Timestamp de ingesta

✅ Preservación histórica

✅ Sin validaciones ni transformaciones

🥈 Silver Layer

Propósito: Limpieza y estandarización

Tablas:

silver_hybrid_manufacturing

silver_manufacturing_defects

Características:

✅ Tipos de datos corregidos

✅ Columnas normalizadas

✅ Manejo de nulos y duplicados

✅ Reglas básicas de calidad

🥇 Gold Layer

Propósito: Analytics-ready

Tablas:

gold_hybrid_manufacturing

gold_manufacturing_defects

KPIs y Métricas:

Producción total por planta y período

Eficiencia del proceso

Defectos por tipo y severidad

Tasa de defectos por línea de producción

Métricas listas para Power BI

Características:

✅ Pre-agregaciones

✅ Optimizado para BI

✅ Alto performance

✅ Consumo directo por SQL / Power BI

📁 Estructura del Proyecto
PROJECT_MANUFACTURING_CICD_MANUFACTURING/
│
├── 📂 .github/
│   └── 📂 workflows/
│       └── 📄 deploy-etl.yml              # Pipeline CI/CD Databricks
│
├── 📂 ETL_Project_CarlosF/
│   │
│   ├── 📂 proceso/                        # ETL Medallion
│   │   ├── 🥉 00_bronze_ingest_catalogs.ipynb
│   │   ├── 🥉 01_bronze_hybrid_manufacturing_categorical.ipynb
│   │   ├── 🥉 01_bronze_manufacturing_defect_dataset.ipynb
│   │   ├── 🥈 02_silver_hybrid_manufacturing_categorical.ipynb
│   │   ├── 🥈 02_silver_manufacturing_defect_dataset.ipynb
│   │   ├── 🥇 03_gold_hybrid_manufacturing.ipynb
│   │   ├── 🥇 03_gold_manufacturing_defects.ipynb
│   │   └── 📤 04_load_gold_to_azure_sql.ipynb
│   │
│   ├── 📂 scripts/                        # Preparación de entorno
│   │   └── 🐍 environment_preparation.py
│   │
│   ├── 📂 seguridad/                      # Gobierno y permisos
│   │   └── 🐍 grants.py
│   │
│   ├── 📂 reversion/                      # Reversión de permisos
│   │   └── 🐍 revoke.py
│
└── 📄 README.md


🛠️ Tecnologías
Tecnología	Propósito
Azure Databricks	Procesamiento distribuido con Spark
Delta Lake	Storage con ACID y versionado
PySpark	Transformaciones ETL
Unity Catalog	Gobierno de datos y permisos
ADLS Gen2	Data Lake
Azure SQL Database	Capa de consumo
Power BI	Visualización
GitHub Actions	CI/CD
⚙️ Requisitos Previos

☁️ Cuenta de Azure

💻 Workspace de Azure Databricks

🧱 Unity Catalog configurado

🖥️ Cluster activo

🐙 Cuenta de GitHub

📦 Azure Data Lake Storage Gen2

📊 Power BI Desktop

🚀 Instalación y Configuración
1️⃣ Clonar el repositorio
git clone https://github.com/tu-org/etl-manufacturing.git
cd etl-manufacturing

2️⃣ Configurar Token de Databricks

Databricks → User Settings → Developer → Access Tokens
Generar token y guardarlo de forma segura.

3️⃣ Configurar GitHub Secrets
Secret	Descripción
DATABRICKS_HOST	URL del workspace
DATABRICKS_TOKEN	Token de acceso
DATABRICKS_CLUSTER	Nombre del cluster
💻 Uso
🔄 Despliegue Automático (Recomendado)
git add .
git commit -m "feat: mejoras pipeline manufactura"
git push origin main


GitHub Actions ejecutará:

📤 Deploy de notebooks

🔧 Creación / actualización del workflow

▶️ Ejecución Bronze → Silver → Gold

📤 Publicación a Azure SQL

🔧 Ejecución Manual en Databricks

Ejecutar en orden:

1. Bronze notebooks

2. Silver notebooks

3. Gold notebooks

4. publish_gold_to_sql.py

🔄 CI/CD
Pipeline GitHub Actions
Deploy notebooks
Validación de cluster
Creación de Databricks Workflow
Ejecución automática

Contacto:
Carlos Andres Fernandez Cerdas
Correo: cfercer96@gmail.com



