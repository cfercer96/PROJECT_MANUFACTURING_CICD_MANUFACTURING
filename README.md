# 🏭 Manufacturing Analytics ETL Pipeline

## Arquitectura Medallion en Azure Databricks

Azure Databricks · PySpark · Delta Lake · Unity Catalog · Azure SQL · Power BI · CI/CD

Pipeline automatizado de datos para el **análisis de procesos productivos y defectos de manufactura**, implementado con arquitectura **Bronze–Silver–Gold**, gobierno de datos con **Unity Catalog** y consumo analítico en **Power BI**.

---

## 🎯 Descripción

Pipeline ETL **enterprise-grade** que procesa datasets de manufactura (producción híbrida y defectos), transformando datos crudos en **datasets analíticos listos para BI**.

El proyecto implementa la **Arquitectura Medallion** sobre **Azure Databricks + Delta Lake**, asegurando **ACID**, versionado, control de accesos y trazabilidad completa, con publicación final en **Azure SQL Database** para consumo desde **Power BI**.

---

## ✨ Características Principales

- 🔄 **ETL Automatizado** – Pipelines orquestados con Databricks Workflows  
- 🏗️ **Arquitectura Medallion** – Bronze → Silver → Gold  
- 🧱 **Delta Lake** – ACID transactions, schema evolution y time travel  
- 🔐 **Unity Catalog** – Gobierno de datos y permisos por capa  
- 📊 **Power BI Ready** – Gold optimizado para visualización  
- 🚀 **CI/CD** – Deploy automatizado desde GitHub Actions  
- 📈 **KPIs de Manufactura** – Métricas listas para análisis operativo  
- 🔔 **Monitoreo** – Logs y control de ejecuciones  

---

## 🏛️ Arquitectura

### Flujo de Datos


📄 CSV / Raw Data
      ↓
🥉 Bronze Layer (Ingesta sin transformación)
      ↓
🥈 Silver Layer (Limpieza y estandarización)
      ↓
🥇 Gold Layer (KPIs y métricas de negocio)
      ↓
🗄️ Azure SQL Database
      ↓
📊 Power BI Dashboards


## 📦 Capas del Pipeline

### 🥉 Bronze Layer

**Propósito:** Zona de aterrizaje (raw)

**Notebooks:**
- `00_bronze_ingest_catalogs.ipynb`
- `01_bronze_hybrid_manufacturing_categorical.ipynb`
- `01_bronze_manufacturing_defect_dataset.ipynb`

**Características:**
- Datos tal como vienen de origen  
- Timestamp de ingesta  
- Preservación histórica  
- Sin validaciones  

---

### 🥈 Silver Layer

**Propósito:** Limpieza y normalización

**Notebooks:**
- `02_silver_hybrid_manufacturing_categorical.ipynb`
- `02_silver_manufacturing_defect_dataset.ipynb`

**Características:**
- Tipos de datos corregidos  
- Columnas estandarizadas  
- Manejo de nulos y duplicados  
- Reglas básicas de calidad  

---

### 🥇 Gold Layer

**Propósito:** Analytics-ready

**Notebooks:**
- `03_gold_hybrid_manufacturing.ipynb`
- `03_gold_manufacturing_defects.ipynb`

**KPIs Principales:**
- Producción total por período  
- Eficiencia del proceso  
- Defectos por tipo y severidad  
- Tasa de defectos por línea  

**Características:**
- Pre-agregaciones  
- Optimizado para BI  
- Alto performance  

---

### 📤 Publicación a Azure SQL

**Notebook:**
- `04_load_gold_to_azure_sql.ipynb`

**Funcionalidad:**
- Escritura de tablas Gold en Azure SQL Database  
- Esquema optimizado para consumo BI  
- Conexión directa desde Power BI

---

### **Estructura del proyecto**

<img width="490" height="454" alt="image" src="https://github.com/user-attachments/assets/e055147e-7b8b-4535-94a1-948f4851e504" />

## 🛠️ Tecnologías

| Tecnología | Propósito |
|-----------|----------|
| Azure Databricks | Procesamiento distribuido |
| PySpark | Transformaciones ETL |
| Delta Lake | ACID y versionado |
| Unity Catalog | Gobierno de datos |
| ADLS Gen2 | Data Lake |
| Azure SQL Database | Capa de consumo |
| Power BI | Visualización |
| GitHub Actions | CI/CD |

---

## 🚀 Uso

**Orden de ejecución del pipeline:**
1. Bronze  
2. Silver  
3. Gold  
4. Load to Azure SQL  

---

## 🔄 CI/CD

Pipeline automatizado con **GitHub Actions**:
- Deploy de notebooks  
- Creación / actualización de workflows  
- Ejecución del pipeline  
- Monitoreo y logs  

---

## 📈 Dashboards

Dashboards construidos en **Power BI**, consumiendo tablas **Gold** desde **Azure SQL Database** para análisis operativo y estratégico.

---

## 🔍 Monitoreo

**Databricks:**
- Workflows → Historial de ejecuciones  
- Logs por tarea  

**GitHub Actions:**
- Tab Actions  
- Logs por ejecución  

---

## 👤 Autor

**Carlos Fernandez**  
Data Engineer
