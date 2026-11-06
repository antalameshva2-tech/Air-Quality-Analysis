<h1 align="center">🌫️ Air Quality Analysis & Visualization</h1>

<p align="center"><em>When, where and why does the air turn unhealthy?</em></p>

<p align="center">
  <strong>A Python-Based Analysis of Hourly Air Quality and Weather Data from 12 Beijing Monitoring Stations</strong>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Python-Data%20Analysis-blue?style=for-the-badge&logo=python" alt="Python" />
  <img src="https://img.shields.io/badge/Pandas-Data%20Processing-150458?style=for-the-badge&logo=pandas" alt="Pandas" />
  <img src="https://img.shields.io/badge/NumPy-Numerical%20Computing-013243?style=for-the-badge&logo=numpy" alt="NumPy" />
  <img src="https://img.shields.io/badge/Matplotlib-Visualization-orange?style=for-the-badge" alt="Matplotlib" />
  <img src="https://img.shields.io/badge/Seaborn-Statistical%20Visualization-76B900?style=for-the-badge" alt="Seaborn" />
</p>

<p align="center">Developed by <strong>Meshva Antala</strong></p>

---

## 📑 Table of Contents

- [Project Overview](#-project-overview)
- [Objectives](#-objectives)
- [Features](#-features)
- [Dataset Information](#-dataset-information)
- [Technologies Used](#-technologies-used)
- [Analysis Performed](#-analysis-performed)
- [Key Findings](#-key-findings)
- [Visualizations](#-visualizations)
- [Project Structure](#-project-structure)
- [Installation](#-installation)
- [How to Run](#-how-to-run)
- [Expected Output](#-expected-output)
- [Limitations](#-limitations)
- [Future Scope](#-future-scope)
- [Conclusion](#-conclusion)
- [Acknowledgements](#-acknowledgements)
- [Author](#-author)

---

## 📌 Project Overview

Air Quality Analysis and Visualization is a Python-based data analysis project that explores hourly air quality and weather data from 12 monitoring stations in Beijing. It uses Pandas and NumPy to clean and process the data and Matplotlib and Seaborn to create visualizations.

The project demonstrates a practical workflow for inspecting a dataset, handling missing values, calculating a daily Air Quality Index (AQI), studying pollution trends over time, comparing stations, understanding the effect of weather, and presenting findings through charts.

## 🎯 Objectives

- Explore hourly air quality and weather data from 12 Beijing stations.
- Inspect dataset structure, columns, and data quality, including missing values and duplicates.
- Study pollution trends by hour, month, season, and year.
- Calculate a daily AQI from PM2.5 and PM10 and group days into AQI categories.
- Compare the stations and identify the most and least polluted areas.
- Examine how wind speed, wind direction, rain, and temperature affect pollution.
- Measure how often the air reaches unhealthy levels.
- Present analytical results through clear visualizations.

## ✨ Features

- Data cleaning and missing value handling
- Descriptive statistics and correlation analysis
- Outlier detection using the IQR method
- Daily AQI calculation and AQI categories
- Hourly, monthly, seasonal, and yearly trend analysis
- Station-wise comparison and station profiling (High / Medium / Low pollution)
- Weather relationship analysis (wind, rain, temperature, wind direction)
- Public health view based on unhealthy days
- Visualizations using Matplotlib and Seaborn

## 📂 Dataset Information

The project uses hourly air quality and weather data from 12 monitoring stations in Beijing.

| Attribute | Details |
|---|---|
| City | Beijing, China |
| Stations | 12 |
| Start Date | March 2013 |
| End Date | February 2017 |
| Frequency | Hourly |
| File Format | CSV (`beijing_air_quality_stations.csv`) |
| Source | Beijing Multi-Site Air-Quality Data (UCI Machine Learning Repository), collected from the Beijing Municipal Environmental Monitoring Center |

### Dataset Columns

| Column | Description |
|---|---|
| `year`, `month`, `day`, `hour` | Date and time of the reading |
| `station` | Name of the monitoring station |
| `PM2.5`, `PM10` | Fine and coarse particulate matter concentration |
| `SO2`, `NO2`, `CO`, `O3` | Concentration of other pollutant gases |
| `TEMP` | Temperature |
| `PRES` | Air pressure |
| `DEWP` | Dew point temperature |
| `RAIN` | Rainfall |
| `WSPM` | Wind speed |
| `wd` | Wind direction |

Use the exact column names present in your CSV file when working with the dataset.

## 🛠️ Technologies Used

- **Python** — Main programming language.
- **Pandas** — Data loading, cleaning, grouping, pivot tables, and resampling.
- **NumPy** — Conditions, interpolation for AQI, and numerical statistics.
- **Matplotlib** — Creating and customizing charts.
- **Seaborn** — Statistical visualizations and heatmaps.
- **Jupyter Notebook** — Writing and running analysis interactively.

## 📊 Analysis Performed

### Dataset Inspection
Inspect the first records, column names, data types, and summary statistics.

### Data Cleaning and Preparation
Fill missing numeric values with the column mean and missing wind direction with the most common value, remove duplicate rows, and create `Date` and `Datetime` columns from year, month, day, and hour.

### Daily AQI Calculation
The daily AQI is the higher of the PM2.5 and PM10 sub-indices of the daily average.

| AQI | Category |
|---|---|
| 0–50 | 🟢 Good |
| 51–100 | 🟡 Satisfactory |
| 101–200 | 🟠 Moderate |
| 201–300 | 🔴 Poor |
| 301–400 | 🟣 Very Poor |
| 401–500 | 🟤 Severe |

### Trend and Seasonal Analysis
Study monthly and yearly trends, the hour-of-day pattern, pollutant-wise monthly trends, and how AQI changes by month and season.

### Station Comparison
Compare average AQI and PM2.5 across stations, build a station × year heatmap, and classify stations as High, Medium, or Low pollution.

### Weather Relationship Analysis
Use correlation and group comparisons to study wind speed, wind direction, rain, and temperature against pollution levels.

### Public Health View
Days in the Poor, Very Poor, or Severe categories are treated as unhealthy days. The analysis checks unhealthy days by station and season, and days above the WHO PM2.5 guideline (15 µg/m³). AQI category shows a health risk level, not real health data such as hospital records.

## 🔍 Key Findings

> Numbers are approximate. Exact values depend on how missing data is handled (this notebook fills them with the mean).

- 📉 Average AQI fell from about **173 (2014)** to **156 (2015)** and **143 (2016)**.
- ❄️ **Winter** is the most polluted season (AQI ≈ 177) and **summer** the cleanest (≈ 134).
- 🧪 PM2.5, PM10, SO2, NO2 and CO peak from **December to March**, while O3 peaks in **June–July**.
- 📍 **Dongsi** and **Gucheng** are the most polluted stations; **Dingling** and **Huairou** are the cleanest.
- 🌬️ **Wind speed** has the strongest link with AQI (correlation ≈ -0.37): AQI is about **238** when wind is below 1 m/s and about **74** when it is above 3 m/s.
- 🧭 North-west winds bring the cleanest air; east and east-south-east winds bring the most polluted air.
- 🌡️ Temperature has a weak effect, and rain days are only slightly cleaner than dry days.

## 📈 Visualizations

The notebook includes the following visualizations:

- Correlation heatmap
- Monthly and yearly PM2.5 and AQI trends
- Hour-of-day pollution pattern
- Average PM2.5 and AQI by station
- Station × year AQI heatmap
- Station pollution segmentation (scatter plot)
- AQI by month and season (box plots)
- Monthly trend of each pollutant and a month-wise heatmap
- Wind speed, wind direction, rain, and temperature versus pollution
- AQI category share by year and by season
- Unhealthy days by station and season

## 📁 Project Structure

```text
Air-Quality-Analysis/
├── Air_Quality_Analysis.ipynb           # Main notebook (full analysis)
├── beijing_air_quality_stations.csv     # Dataset (all 12 stations combined)
└── README.md                            # Project documentation
```

| File / Folder | Description |
|---|---|
| `Air_Quality_Analysis.ipynb` | Jupyter Notebook with the complete analysis |
| `beijing_air_quality_stations.csv` | Hourly air quality and weather data of the 12 stations |
| `README.md` | Project documentation |

Make sure the folder and filenames match the files in your repository.

## ⚙️ Installation

### Prerequisites

- Python 3.9 or newer
- Jupyter Notebook or Visual Studio Code

### 1. Clone the Repository

```bash
git clone <your-repository-link>
```

### 2. Open the Project Folder

```bash
cd Air-Quality-Analysis
```

### 3. Install the Required Libraries

```bash
pip install pandas numpy matplotlib seaborn jupyter
```

## ▶️ How to Run

1. Open a terminal in the project folder.
2. Start Jupyter Notebook:

   ```bash
   jupyter notebook
   ```

3. Open `Air_Quality_Analysis.ipynb`.
4. Select the correct Python environment.
5. Choose **Kernel → Restart & Run All**, or run the cells in order.
6. Review the generated tables, statistics, and charts.

You can also open the project folder in Visual Studio Code and run the notebook using the Jupyter extension.

> ℹ️ `resample("ME")` needs pandas 2.2 or newer.

## 🖥️ Expected Output

Depending on the code in the notebook, the output includes:

- A preview of the air quality dataset
- Missing value and data quality checks
- Descriptive statistics and correlation matrix
- Daily AQI and AQI categories
- Station comparison tables and station categories
- Trend, seasonal, and weather relationship charts
- Unhealthy days by station and season
- Conclusions based on the analysis

## ⚠️ Limitations

- AQI uses only PM2.5 and PM10 (not SO2, NO2, CO, O3).
- Mean-filling of missing values can slightly flatten extreme readings.
- 2013 starts in March and 2017 covers only January–February, so yearly comparisons use 2014–2016.
- Correlation does not establish a cause-and-effect relationship.
- The analysis is for educational purposes only.

## 🚀 Future Scope

- 🤖 Predict next-day AQI using regression or time-series models.
- 🧮 Include all pollutants in the AQI calculation.
- 🗺️ Map the stations on an interactive map.
- 📊 Build an interactive dashboard with Streamlit or Power BI.
- 🔄 Use interpolation or model-based imputation for missing values.

## 🏁 Conclusion

This project demonstrates how Python libraries can be used to analyze air quality data and communicate findings through visualizations. It applies data cleaning, AQI calculation, statistical analysis, and charting techniques to explore pollution in Beijing.

The analysis shows that air quality improved over the study period, but pollution remains high in winter and on low-wind days, and that weather, especially wind, plays a major role. The project provides practical experience with Python, Pandas, NumPy, Matplotlib, and Seaborn and builds a foundation for further work in data analytics and environmental data analysis.

## 🙏 Acknowledgements

- Dataset: Beijing Multi-Site Air-Quality Data, available from the UCI Machine Learning Repository.
- AQI categories follow the CPCB (India) style bands for PM2.5 and PM10.
- WHO Air Quality Guidelines (PM2.5 24-hour value of 15 µg/m³) are used as a health reference.
- Libraries: Pandas, NumPy, Matplotlib, Seaborn and Jupyter.

## 👩‍💻 Author

**Meshva Antala**

Python | Data Analysis | Data Visualization

---

<p align="center">Thank you for visiting this project! ⭐</p>
