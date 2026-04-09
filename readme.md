# Azure End-to-End Data Engineering Pipeline

This project demonstrates a robust, enterprise-grade data engineering pipeline built on the **Microsoft Azure Cloud** platform. It covers the entire lifecycle of data—from ingestion from external sources to final visualization—while emphasizing security, monitoring, and version control.

---

## 🏗️ Architecture Overview

The pipeline follows a structured "Medallion-style" flow to ensure data reliability and scalability:

1.  **Ingestion**: Data is pulled from **External Sources** using **Azure Data Factory (ADF)** with a **Self-Hosted Integration Runtime (SHIR)** for secure connectivity.
2.  **Storage (Raw)**: The ingested data is stored in its native format in **Azure Data Lake Storage (ADLS) Gen2**.
3.  **Transformation**: **Azure Databricks** performs data cleaning and complex transformations, utilizing **Secret Scopes** and **Azure Key Vault** for secure credential management.
4.  **Serving**: The transformed data is loaded back into **ADLS Gen2** and then into **Azure Synapse Analytics** for high-performance SQL querying.
5.  **Visualization**: Final insights are delivered via a **Power BI** dashboard.

---

## 🛠️ Tech Stack & Tooling

| Component | Service | Purpose |
| :--- | :--- | :--- |
| **Orchestration** | Azure Data Factory | Data movement and pipeline scheduling |
| **Compute** | Azure Databricks | Spark-based data cleaning and processing |
| **Storage** | Azure Data Lake Gen2 | Scalable storage for raw and transformed data |
| **Data Warehouse** | Azure Synapse Analytics | Relational data serving and SQL querying |
| **Security** | Azure Key Vault | Management of secrets and credentials |
| **Monitoring** | Azure Monitor & Logic Apps | Real-time alerts and automated email notifications |
| **CI/CD** | GitHub | Version control for code and pipeline templates |
| **BI** | Power BI | Interactive reporting and dashboards |

---

## 🚀 Key Features

* **Secure Credential Management**: Integration of **Azure Key Vault** with **Databricks Secret Scopes** ensures no hardcoded credentials exist in notebooks.
* **Automated Notifications**: **Logic Apps** are configured to trigger email alerts upon pipeline success or failure, ensuring high reliability.
* **Hybrid Connectivity**: Uses **SHIR (Self-Hosted Integration Runtime)** to securely bridge the gap between external/on-premise data sources and the Azure cloud.
* **Version Controlled**: All pipeline definitions and transformation scripts are synced with this **GitHub repository** for CI/CD readiness.

---

## 📁 Repository Structure

* `/arm-templates`: Azure Resource Manager templates for infrastructure deployment.
* `/databricks-notebooks`: PySpark/SQL notebooks used for data transformation.
* `/sql-scripts`: DDL and DML scripts for Azure Synapse tables.
* `/config`: Logic App workflows and Monitoring configurations.

---

## 🚦 Getting Started

1.  **Clone the Repo**: 
    ```bash
    git clone [[((https://github.com/Harshvir007/AzureDataPipeline/))]]
    ```
2.  **Setup Key Vault**: Add your connection strings and secrets to Azure Key Vault.
3.  **Configure ADF**: Import the JSON pipeline definitions and link your SHIR.
4.  **Mount Data Lake**: Run the setup notebook in Databricks to mount your ADLS Gen2 containers.
5.  **Trigger Pipeline**: Manually trigger the ADF pipeline to validate the end-to-end flow.

---

## 📈 Monitoring & Reliability
The pipeline includes built-in monitoring via **Azure Monitor**. If a stage fails, **Logic Apps** automatically sends a status email to the data engineering team with the specific error logs for

