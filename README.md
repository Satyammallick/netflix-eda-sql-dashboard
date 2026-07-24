# 🎬 Netflix Content Strategy & Data Pipeline

![Language](https://img.shields.io/badge/Language-Python%20%28Pandas%2C%20NumPy%29-orange)
![Tool](https://img.shields.io/badge/Visualization-Power_BI-yellow)
![Analysis](https://img.shields.io/badge/Process-EDA%20%26%20Data%20Cleaning-blue)
![Status](https://img.shields.io/badge/Status-Completed-success)

An end-to-end data cleaning, exploratory data analysis (EDA), and business visualization project analyzing Netflix's global content catalog. Using **Python** for data preprocessing and exploratory auditing, and **Power BI** for interactive executive reporting, this project evaluates content acquisition trends, regional production dynamics, runtime patterns, and audience demographics to deliver strategic recommendations.

---

## 🖼️ Dashboard Preview

![Netflix Content Dashboard](images/dashboard_overview.png)
*Figure 1: Interactive Power BI Dashboard tracking content distribution, regional production, rating breakdown, and release year trends.*

---

## 📁 Repository Structure

```text
netflix_content_strategy/
├── 📄 README.md                        # Project documentation & repository guide
├── 📄 business_insights.md             # Detailed findings & strategic content recommendations
├── 📁 dataset/
│   ├── 📄 netflix_titles_raw.csv       # Raw Kaggle Netflix catalog dataset
│   └── 📄 netflix_titles_cleaned.csv   # Cleaned & processed dataset ready for Power BI
├── 📁 images/
│   └── 📄 dashboard_overview.png       # Power BI executive report preview
├── 📁 notebooks/
│   └── 📄 netflix_eda_and_cleaning.ipynb # Jupyter notebook containing Python data cleaning & EDA
└── 📁 power_bi/
    └── 📄 netflix_strategy_dashboard.pbix # Interactive Power BI dashboard file
## 🐍 Python Data Cleaning & EDA Highlights

Executed in `notebooks/netflix_eda_and_cleaning.ipynb`:

* **Missing Value Imputation:** Handled `NULL` values in key categorical attributes (`director`, `cast`, and `country`) to prevent data loss during aggregation.
* **Date Standardization:** Converted string-based `date_added` into standard `datetime` objects, extracting `year_added` and `month_added` features.
* **Duration Feature Engineering:** Separated duration strings (e.g., `"90 min"`, `"2 Seasons"`) into structured numerical features (`duration_min` for Movies, `seasons` for TV Shows).
* **Exploratory Visualizations:** Generated distribution plots and correlation maps to detect catalog shifts, runtime distributions, and missing data density.

---

## 🗄️ SQL Analytics & Data Modeling

Executed in `sql_queries/`:

* **Multi-Value Unnesting:** Used CTEs and string-splitting functions (`STRING_SPLIT` / `UNNEST`) to explode delimited strings in `cast`, `listed_in` (genres), and `country` for clean relational joins.
* **Release Velocity Analysis:** Calculated year-over-year catalog growth rates and content type ratios using window functions (`LAG`, `SUM OVER`).
* **Regional Production Matrix:** Ranked top genres by country using `DENSE_RANK()` to isolate regional preferences and production dominance.

---

## 📊 Power BI Dashboard Features

Built in `power_bi/netflix_strategy_dashboard.pbix`:

* **Top-Level KPI Cards:** Key performance metrics including Total Titles, Total Movies, Total TV Shows, and Total Production Countries.
* **Dynamic Content Distribution:** Visualizing Movie vs. TV Show ratios and historical trajectory across release years.
* **Geographic Map / Bar Visuals:** Highlighting top content-producing hubs (US, India, UK, South Korea, Japan).
* **Demographic & Genre Breakdown:** Donut and bar charts detailing rating distribution (`TV-MA`, `TV-14`, etc.) and top-performing categories.

---

## 🗄️ Dataset Overview & Schema

Located in `dataset/netflix_titles_cleaned.csv`, the dataset contains processed title metadata:

| Column Name | Data Type | Description |
| :--- | :--- | :--- |
| `show_id` | `VARCHAR(10)` | Unique identifier for each title |
| `type` | `VARCHAR(15)` | Classification (Movie or TV Show) |
| `title` | `VARCHAR(255)` | Name of the movie or show |
| `director` | `VARCHAR(255)` | Director(s) associated with the title |
| `cast` | `TEXT` | Lead actors / cast members |
| `country` | `VARCHAR(255)` | Primary country of production |
| `date_added` | `DATE` | Date added to the Netflix catalog |
| `release_year` | `INTEGER` | Original release year |
| `rating` | `VARCHAR(10)` | Maturity / MPAA rating (e.g., TV-MA, PG-13) |
| `duration_val` | `INTEGER` | Numeric duration value |
| `duration_unit` | `VARCHAR(10)` | Unit of duration (Minutes or Seasons) |
| `listed_in` | `TEXT` | Genres & catalog classifications |
