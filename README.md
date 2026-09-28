# Houston Police Department (HPD) Crime Analysis (2025)

An exploratory data analysis and feature engineering pipeline for Houston crime incident data from the year 2025 (`NIBRSPublicView2025_Divisions.parquet`)[cite: 1]. This project cleans raw NIBRS (National Incident-Based Reporting System) public safety records, optimizes memory footprints, builds robust temporal/contextual features, and uncovers spatial-behavioral insights across Houston police divisions.

---

## 📊 Dataset Overview & Cleaning
* **Volume:** Analyzes **240,661 recorded crime incidents** spanning the entirety of 2025[cite: 1].
* **Memory Optimization:** Optimized the DataFrame memory footprint down to ~13 MB by casting variables into efficient data types (`category`, `datetime64`, `int8`)[cite: 1].
* **Data Quality Notes:** Identified minor missingness in spatial coordinate fields (`map_longitude`, `map_latitude` with 3,684 missing values) and specific street details (`street_type`, `street_suffix`)[cite: 1].

---

## ⚙️ Engineered Features
To enable granular temporal, seasonal, and spatial modeling, the data pipeline extracts and constructs the following attributes:
* **Temporal Components:** `year`, `month`, `day`, `day_of_week`, `day_name`, `day_of_year`, and `week_num`[cite: 1].
* **Custom Weekend Flag (`is_weekend`):** A custom boolean flag designed to capture true weekend crime dynamics by accounting for Friday evenings (from 5:00 PM onward) through Sunday[cite: 1].
* **Contextual & Environmental Markers:** 
  * Meteorological `season` classification[cite: 1].
  * Daily `time_block` partitions[cite: 1].
  * A `holiday_name` indicator covering US federal holidays and major cultural events (e.g., Super Bowl Sunday, Halloween)[cite: 1].
* **Schema Structure:** Final cleaned dataset consists of **29 structured columns** (~16 MB)[cite: 1].

---

## 📈 Exploratory Data Analysis (EDA) Highlights
* **Dominant Offense Types:** Top recurring crimes include offenses like *Simple Assault*, mapped across urban environments[cite: 1].
* **Geographic Distribution:** Incident concentration tracked across major police divisions (such as *Southeast*)[cite: 1].
* **Bivariate Insights:** Utilizes cross-tabulation matrices and Seaborn heatmaps to cross-reference top crime descriptions with specific premise types (e.g., residences, highways, commercial spaces)[cite: 1].

---

## 🛠️ Project Structure & Requirements
* **Primary Notebook:** `hpd_analysis.ipynb`[cite: 1]
* **Data Source:** `NIBRSPublicView2025_Divisions.parquet`[cite: 1]
* **Python Environment:** Managed via virtual environment (`.venv`) utilizing standard data science libraries (`pandas`, `numpy`, `matplotlib`, `seaborn`, `pyarrow`).