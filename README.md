
# 🏖️ Bathing Water Quality in Europe (1990–2024)
**Analyse der Badegewässerqualität in Europa**

This project explores the evolution, distribution, and classification of bathing water quality across Europe over a period of 35 years using a dataset of over 672,000 records. It includes time-series analysis, geospatial mapping, and country-wise comparisons.

---

## 📌 Project Overview

- **Title**: Analysis of Bathing Water Status Across Europe  
- **Time Range**: 1990–2024  
- **Data Size**: 672,629 entries  
- **Dataset**: `bw_assessment_eea_datahub_1990_2024.csv`

---

## 🎯 Objectives

- Track how bathing water quality evolved over time  
- Compare regional and national trends  
- Detect zones with consistently poor or excellent ratings  
- Leverage maps and charts for intuitive visual understanding  

---

## 📊 Dataset Fields

- `'countryCode'` – ISO country code  
- `'bathingWaterIdentifier'` – Unique ID for each bathing site  
- `'groupIdentifier'` – Optional group/clustering ID for nearby sites  
- `'bathingWaterName'` – Name of the bathing site  
- `'bathingWaterType'` – Inland or coastal  
- `'geographicalConstraint'` – Classification based on EU definitions  
- `'lon'`, `'lat'` – Geographic coordinates  
- `'bwProfile'` – Description or profile of the bathing water  
- `'season'` – Year in which quality was assessed  
- `'quality'` – Assigned quality category (e.g., Excellent, Good, Poor)  
- `'monitoringCalendar'` – Optional testing calendar info  
- `'management'` – Optional site management strategy  

---

## 🔍 Data Exploration & Preprocessing

- Cleaned missing or invalid values in key fields  
- Disabled output truncation for full inspection in Pandas  
- Used `.unstack()` and `.size()` to reformat and summarize group data  
- Generated sample maps with `folium` to check geolocation accuracy  

---

## 📈 Key Analyses

### 1. 🗺️ Geospatial Mapping
- Sampled over 1,000 locations and displayed using `folium`  
- Color-coded by water quality  
- **Output file**: `maps/bathing_water_quality_map.html`

### 2. 📊 Country-Level Analysis
- Identified countries with the most bathing sites  
- Computed mean latitude/longitude to observe geographic clustering  
- Calculated share of each quality class per country (normalized)

### 3. 📅 Time Series Analysis
- Tracked share of "Excellent" sites from 1990 to 2024  
- Used stacked bar charts to show yearly quality distributions  
- Highlighted long-term trends and potential improvement/decline zones  

### 4. 🏆 Top and Worst Performing Sites
- Listed most consistently "Excellent" sites  
- Flagged sites frequently classified as "Poor"  
- Included filtering options by name or country for deeper inspection  

---

## 💡 Sample Plots & Outputs

- Bathing water quality distribution per year (stacked bar chart)  
- "Excellent" share over time (line plot)  
- Clustered site coordinates by country  
- Interactive `folium` maps with color-coded legends  

---

## ⚙️ Code Highlights

- Used `.unstack()` to pivot group-level data  
- Applied `.size()` instead of `.count()` to include NaN tracking  
- Normalized country-specific values using `.div(..., axis=0)`  
- Chained operations like `.groupby()`, `.size()`, `.sort_values()` for clarity and efficiency  

---

## 🧱 Recommended Repository Structure

```txt
/bathing-water-quality/
├── bathing_water_quality_analysis.ipynb     
├── data/
│   └── bathing_water_quality_dataset.csv    
├── charts/
│   ├── output_01.png                      
│   └── output_02.png
├── maps/
│   └── bathing_water_quality_map.html      
├── README.md                              
└── .gitignore                              
```
---

## 📦 Dependencies
```txt
pandas
matplotlib
seaborn
folium
```
---

## 📜 License

This project uses data provided by the European Environment Agency (EEA).
Please consult the EEA’s official data policy for reuse and citation rules.

---

## ✍️ Author & Contact

Author: Vasily Z.

Contact: [info.abw.net@gmail.com](mailto:info.abw.net@gmail.com)
