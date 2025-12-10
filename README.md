# 🎬 ETL Pipeline de Películas con Azure Databricks (Arquitectura Medallion + CI/CD)

Este proyecto implementa un **Pipeline ETL de análisis de películas**, utilizando la **arquitectura Medallion (Bronze → Silver → Gold)** en **Azure Databricks**, con integración a múltiples servicios en Azure, gobernanza de datos, y despliegue automatizado mediante **CI/CD con GitHub Actions**.

📌 Dataset utilizado:  
**Which Movie Should I Watch Today?**  
Fuente: Kaggle → https://www.kaggle.com/datasets/hassanelfattmi/which-movie-should-i-watch-today

---

## 🚀 Objetivo del Proyecto

Construir un **pipeline de datos moderno**, el cual:

✔ Consuma datos desde Azure Data Lake (CSV)  
✔ Transforme y limpie información de películas  
✔ Publique datos curados en la capa Gold  
✔ Aplique seguridad con roles, grants y Delta Sharing  
✔ Habilite un dashboard en Power BI  
✔ Automatice deployment de notebooks y workflows con CI/CD

---

## 🏗 Arquitectura Tecnológica

Este proyecto integra los siguientes servicios de Azure:

🔹 **Azure Databricks** (ETL + Medallion Architecture)  
🔹 **Azure Data Lake Storage Gen2** (Datalake)  
🔹 **Azure Key Vault** (Gestión de secretos)  
🔹 **Azure Entra ID** (Autenticación de servicios)  
🔹 **Access Connector for DataBricks** (Security Global Access)  
🔹 **GitHub Actions** (CI/CD para Workflows Databricks)  
🔹 **Power BI Desktop** (Visualización final)  
🔹 **Delta Sharing** (Compartición segura de la capa Gold)

⚙️ Se estableció el acceso utilizando:  
- External Locations  
- Credential Registrations  
- Key Vault Secrets  
- Permisos RBAC y SQL Grants

---

## 🔄 Flujo ETL (Arquitectura Medallion)

| Capa | Descripción | Resultado |
|------|-------------|-----------|
| 🟫 **Bronze** | Ingesta cruda desde CSV del Data Lake RAW | Tablas sin transformación |
| 🥈 **Silver** | Limpieza, cast de tipos, join, normalización | Datos listos para consumo analítico |
| 🥇 **Gold** | Modelo final optimizado para análisis | Dataset consumido por Power BI y Delta Sharing |

📌 Archivos consumidos:  
- `movies.csv`  
- `poster.csv`  
- `movie_details.csv`  
- `more_info.csv`

---

## 🔐 Seguridad y Gobernanza

🔒 Implementación de permisos avanzados:

| Recurso | Control |
|--------|--------|
| Catálogos, esquemas y tablas | Grants basados en roles |
| Secretos | Azure Key Vault |
| External Locations | Storage + Access Connector |
| Compartición de datos | Delta Sharing |

---

## 🔁 CI/CD – Despliegue Automático

En la carpeta `.github/workflows` se encuentra el workflow que:

✔ Recrea Workflows de Databricks en PROD  
✔ Versiona notebooks y scripts en repos  
✔ Ejecuta el pipeline completo de forma automatizada  
✔ Realiza rollback si ocurre un error

🧾 **El YAML permite:**
- Definir Jobs  
- Declarar dependencias  
- Aplicar despliegue controlado por ambiente  

---

## 📂 Estructura del Repositorio

```
📦 ETL-Peliculas
│
├── 📊 Dashboard/                     → Reporte Power BI (.pbix)
├── 🔙 Reversion/                     → Script de reversión (Rollback completo)
├── 🔐 Seguridad/                     → Grants, Delta Sharing, gobernanza
├── ⚙️ .github/workflows/             → CI/CD deployment Dev → Prod
├── 🧠 Scripts/                       → Preparación de ambiente (PySpark)
├── 🔄 Proceso/                       → ETL en notebooks (Bronze/Silver/Gold)
├── 🏅 Certificaciones/               → Evidencias del curso / certificaciones
└── README.md
```

---

## 📊 Dashboard Power BI

El archivo `.pbix` muestra:

🎞 Recomendación de películas  
📈 Distribución por género  
⭐ Promedio de puntuaciones  
🎭 Popularidad y ratings  
📌 Datos provenientes de la **capa Gold en Delta**

---

## 💻 Tecnologías Utilizadas

| Área | Tecnología |
|------|------------|
| ETL | PySpark + Databricks |
| Almacenamiento | ADLS Gen2 |
| Seguridad | Key Vault + Entra ID + AC Databricks |
| DataOps | GitHub Actions |
| Visualización | Power BI |
| Sharing | Delta Sharing |

---

## 🙌 Autor

👨‍💻 **Andrés Gustavo La Rosa Toro Cabrera**  
📌 *Ingeniero de Datos*  

🔗 **LinkedIn:** https://www.linkedin.com/in/glarosatoroc/  
💻 **GitHub:** https://github.com/larosatoro96  
📧 **Correo:** larosatoro979@gmail.com

---

### ⭐ Si te gustó el Proyecto

Puedes apoyar con un **Star** ⭐ al repositorio ¡Muchas gracias!
