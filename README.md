# CICDMOVIESPROJECT
# 🎬 ETL Pipeline de Películas con Azure Databricks  
*Arquitectura Medallion + CI/CD + Power BI*

Este proyecto implementa un pipeline de datos sobre información de películas utilizando la arquitectura **Medallion (Bronze → Silver → Gold)** en **Azure Databricks**, con seguridad empresarial, despliegue automatizado y visualización en Power BI.

**Fuente del dataset:**  
Which Movie Should I Watch Today?  
https://www.kaggle.com/datasets/hassanelfattmi/which-movie-should-i-watch-today

---

## 🚀 Objetivo del Proyecto
Construcción de un pipeline moderno que:

- Consume datos desde Azure Data Lake (CSV)
- Limpia, transforma y normaliza información de películas
- Crea tres capas de procesamiento (Bronze, Silver, Gold)
- Aplica seguridad con Key Vault, RBAC y SQL Grants
- Expone datos a Power BI mediante Delta Sharing
- Automatiza deployment con GitHub Actions (CI/CD)

---

## 🏗️ Arquitectura y Servicios Usados

![Arquitectura de la solución](https://github.com/larosatoro96/CICDMOVIESPROJECT/raw/construccion/ARQUITECTURA.png)

- **Azure Databricks** (ETL + Notebooks)
- **Azure Data Lake Storage Gen2**
- **Azure Key Vault**
- **Azure Entra ID**
- **Access Connector for Databricks**
- **GitHub Actions** (CI/CD)
- **Power BI Desktop**
- **Delta Sharing**

**Gobernanza Implementada:**
- External Locations
- Registro de credenciales
- Seguridad con Key Vault
- Permisos SQL en catálogos, esquemas y tablas

---

## 🔄 Flujo ETL (Medallion)

| Capa | Descripción | Resultado |
|------|-------------|-----------|
| **Bronze** | Ingesta directa desde CSV | Datos sin transformación |
| **Silver** | Limpieza, cast, joins, estandarización | Datos limpios |
| **Gold** | Modelo final para análisis | Dataset consumido en Power BI |

![workflow](https://github.com/larosatoro96/CICDMOVIESPROJECT/raw/construccion/workflow.png)

**Archivos consumidos del RAW:**
- movies.csv
- poster.csv
- movie_details.csv
- more_info.csv

---

## 🔐 Seguridad, Roles y Data Sharing

📌 Seguridad implementada:
- Grants por roles
- Control de acceso en tablas, esquemas y catálogos
- Registro de credenciales en Databricks
- Accesos definidos mediante Azure Entra ID

📌 **Delta Sharing:**  
Se compartió la tabla Gold para consumo externo (Power BI).

---

## 🔁 CI/CD con GitHub Actions

El repositorio contiene un workflow que:
- Recrea Workflows en Databricks
- Despliega notebooks y scripts a PROD
- Ejecuta automáticamente el ETL
- Implementa rollback en caso de error

📌 Ubicación del archivo:
```
.github/workflows/
```

---

## 📂 Estructura del Repositorio

```
📦 ETL-Peliculas
│
├── Dashboard/                 Reporte Power BI (.pbix)
├── Reversion/                 Eliminación de objetos + rollback completo
├── Seguridad/                 Grants, Delta Sharing, roles
├── .github/workflows/         CI/CD Dev → Prod
├── Scripts/                   PySpark para entorno y tablas
├── Proceso/                   Notebooks del ETL (Bronze/Silver/Gold)
├── Certificaciones/           Evidencias de curso
└── README.md
```

---

## 📊 Dashboard Power BI

Incluye:
- Recomendador de películas
- Distribución por género
- Puntaje promedio (user_score)
- Ranking por popularidad
- Visualización de pósteres y backdrop

📌 Fuente: **Tabla Golden mediante Delta Sharing**

---

## 💻 Tecnologías y Herramientas

| Área | Tecnología |
|------|------------|
| ETL | PySpark + Databricks |
| Almacenamiento | ADLS Gen2 |
| Seguridad | Key Vault + Entra ID + Access Connector |
| DataOps | GitHub Actions |
| Visualización | Power BI |
| Sharing | Delta Sharing |

---

## 🙌 Autor

👨‍💻 **Andrés Gustavo La Rosa Toro Cabrera**  
*Ingeniero de Datos*

🔗 LinkedIn: https://www.linkedin.com/in/glarosatoroc/  
💻 GitHub: https://github.com/larosatoro96  
📧 Correo: larosatoro979@gmail.com

---

⭐ *Si te gustó este proyecto, puedes dejar una estrella en el repositorio. ¡Gracias!*
