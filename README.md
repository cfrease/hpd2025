# HPD2025 Crime Data Analysis

An analytical exploration and geospatial workflow examining the Houston Police Department (HPD) 2025 crime dataset. This project leverages structured exploratory data analysis, feature engineering, and division-level modeling to uncover patterns and trends.

## Quick Summary of Findings

* **Volume Drivers**: Police interventions are heavily driven by high-frequency offenses like simple assaults, intimidation, and theft from motor vehicles.
* **Spatial Patterns**: Interpersonal crimes (assaults, intimidation) concentrate near residential properties, while property crimes (theft from motor vehicles) skew toward parking lots, garages, and public roadways.
* **Temporal Trends**: Custom weekend flags and time blocks effectively isolate crime shifts during non-working and leisure windows.
* **Contextual Spikes**: Meteorological seasons and cultural event markers (`holiday_name`) capture seasonal shifts and holiday-driven anomalies.

## Project Overview

- **Objective**: Process, analyze, and visualize crime incident data to extract actionable insights regarding spatial concentrations and temporal trends.
- **Core Dataset**: HPD 2025 incident records containing 240,661 recorded crime incidents across Houston, alongside spatial coordinates, timestamps, offense types, and division details.

## Analysis & Methodology (`hpd_analysis.ipynb`)

- **Data Cleaning & Memory Optimization**: Optimized memory usage down to 13 MB by converting object columns into efficient `category` dtypes, string timestamps into `datetime64[ns]`, and numerical IDs into smaller integers. Identified minor missing data in spatial coordinates (`map_longitude`, `map_latitude` with 3,684 missing entries) and street details (`street_type`, `street_suffix`) that require handling for spatial tasks.
- **Feature Engineering**: Expanded the dataset to 29 columns (~16 MB) with derived temporal attributes (year, month, day, day of week, day of year, week num), meteorological seasons, daily time-block windows, a custom boolean `is_weekend` flag (incorporating Friday evenings from 5:00 PM onward through Sunday), and a `holiday_name` indicator covering US federal holidays and major cultural events (e.g., Super Bowl Sunday, Halloween).
- **Geospatial & Temporal Modeling**: 
  - Identifying high-incident hotspots using coordinate mapping, fully primed for spatial clustering and division-level boundary analysis.
  - Analyzing crime distributions across different hours, days, and seasonal velocity shifts using granular date-time features.
  - Comparing aggregate and category-specific crime metrics across Houston's police divisions.

## Key EDA Findings & Insights

- **Offense Volumetrics**: The dataset is heavily driven by high-frequency offenses. Specifically, simple assaults, intimidation, and theft from motor vehicles make up the vast majority of recorded incidents, dictating the primary volume of daily police department interventions.
- **Spatial Concentration by Location Type**: Cross-tabulations reveal distinct behavioral clustering for different crime types. Violent and interpersonal offenses like simple assaults and intimidation heavily concentrate around residential properties, whereas property crimes such as theft from motor vehicles predominantly occur in transient, public spaces like parking lots, garages, and along highways, roads, streets, or alleys.
- **Temporal & Leisure-Time Shifts**: Utilizing the custom `is_weekend` flag (capturing Friday evenings from 5:00 PM onward through Sunday) alongside daily `time_block` windows effectively isolates peak operational response periods. This granular approach highlights distinct shifts in crime volume during non-working hours and traditional leisure windows.
- **Event-Driven & Seasonal Anomalies**: The integration of meteorological seasons and specialized cultural events (`holiday_name` covering federal holidays, Super Bowl Sunday, and Halloween) establishes critical analytical layers. These features allow analysts to evaluate seasonal velocity changes, weather-driven behavioral shifts, and localized spikes in public disturbances or property crimes during major public celebrations.
