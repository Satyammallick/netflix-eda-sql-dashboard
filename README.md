# 🎬 Netflix Content Strategy & Data Pipeline

![Language](https://img.shields.io/badge/Language-Python-orange)
![Database](https://img.shields.io/badge/Database-SQL-blue)
![Tool](https://img.shields.io/badge/Visualization-Power_BI-yellow)
![Process](https://img.shields.io/badge/Process-ETL%20%7C%20EDA%20%7C%20Analytics-brightgreen)
![Status](https://img.shields.io/badge/Status-Completed-success)

An end-to-end data engineering and analytics solution examining Netflix's global content catalog. The pipeline uses **Python** for data extraction, exploratory data analysis (EDA), and cleaning, **SQL** for relational data modeling and analytical querying, and **Power BI** for executive-level data visualization.

---

## 🖼️ Dashboard Preview

![Netflix Strategy Dashboard](images/dashboard_overview.png)
*Figure 1: Power BI Executive Dashboard tracking content distribution, regional production, rating breakdown, and release velocity.*

---

## 📁 Repository Structure

```text
netflix_content_strategy/
├── 📄 README.md                        # Project documentation & repository guide
├── 📄 business_insights.md             # Detailed executive summary & strategic recommendations
├── 📁 dataset/
│   ├── 📄 netflix_titles_raw.csv       # Raw catalog dataset
│   └── 📄 netflix_titles_cleaned.csv   # Post-ETL normalized data output
├── 📁 images/
│   └── 📄 dashboard_overview.png       # Power BI executive report preview
├── 📁 notebooks/
│   └── 📄 netflix_eda_and_cleaning.ipynb # Jupyter Notebook for Python EDA & cleaning
├── 📁 sql_queries/
│   ├── 📄 01_schema_setup.sql          # Relational table schema setup
│   ├── 📄 02_data_cleaning.sql         # SQL deduplication & data integrity checks
│   ├── 📄 03_genre_cast_unnesting.sql  # Multi-value string unnesting (CTEs/STRING_SPLIT)
│   ├── 📄 04_content_trends.sql        # Release velocity & Movie vs TV Show ratios
│   └── 📄 05_country_genre_matrix.sql  # Window functions for regional insights
└── 📁 power_bi/
    └── 📄 netflix_strategy_dashboard.pbix # Interactive Power BI report file
