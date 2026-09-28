# HPD2025 Crime Data Analysis

An analytical exploration and geospatial workflow examining the Houston Police Department (HPD) 2025 crime dataset. This project leverages structured exploratory data analysis, feature engineering, and division-level modeling to uncover patterns and trends.

## Project Overview
* **Objective**: Process, analyze, and visualize crime incident data to extract actionable insights regarding spatial concentrations and temporal trends.
* **Core Dataset**: HPD 2025 incident records containing spatial coordinates, timestamps, offense types, and division details.

## Analysis & Methodology (`hpd_analysis.ipynb`)
* **Data Cleaning & Preparation**: Standardizing date-time fields, handling missing values, and formatting geographic features.
* **Feature Engineering**: Deriving temporal attributes (hour of day, day of week, seasonal shifts) and spatial identifiers.
* **Geospatial & Temporal Modeling**: 
  * Identifying high-incident hotspots using coordinate mapping.
  * Analyzing crime distributions across different hours and days.
  * Comparing aggregate and category-specific crime metrics across Houston's police divisions.