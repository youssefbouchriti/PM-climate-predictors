# Random Forest-Based Modeling for PM2.5 Prediction in Semi-Arid Morocco

[![R Version](https://img.shields.io/badge/R-4.4.2-blue.svg)](https://www.r-project.org/)
[![License](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE)
[![DOI](https://img.shields.io/badge/DOI-10.xxxx/zenodo.xxxxxx-blue.svg)](https://doi.org/10.xxxx/zenodo.xxxxxx)

## 📌 Overview

This repository contains a **complete, reproducible R script** for predicting annual PM2.5 concentrations from meteorological variables in three Moroccan cities (Agadir, Taroudannt, Tiznit) over the period 2000–2019.

The script implements a **Random Forest model (RFM)** and compares its performance with classical statistical methods (Pearson correlation, simple linear regression) to demonstrate their methodological complementarity.

## 🎯 Key Features

| Feature | Description |
|---------|-------------|
| Data preprocessing | Automated handling of missing values, variable standardization, RF-based bias calibration |
| Random Forest | 500 trees, `mtry = 3`, configurable parameters |
| Cross-validation | 5-fold robust evaluation |
| Variable importance | %IncMSE and IncNodePurity metrics |
| Normality testing | Shapiro-Wilk and Anderson-Darling tests |
| Correlation analysis | Pearson or Spearman (auto-selected based on data distribution) |
| Linear regression | Univariate equations with R² and p-values |
| Visualization | Publication-ready figures (TIFF 600 dpi, EMF) |
| Reproducibility | Fully annotated script with error handling |

## 📊 Input Data

The script expects an Excel file (`PM.xlsx`) with the following annual variables (2000–2019, 3 cities, n = 60 observations):

| Variable | Description | Unit |
|----------|-------------|------|
| `PM` | PM2.5 concentration | µg/m³ |
| `GWETPROF` | Profile soil moisture | - |
| `GWETROOT` | Root zone soil wetness | - |
| `GWETTOP` | Surface soil wetness | - |
| `PRECTOTCORR` | Corrected precipitation | mm/day |
| `PS` | Surface pressure | kPa |
| `RH2M` | Relative humidity at 2 m | % |
| `T2M` | Temperature at 2 m | °C |
| `T2MDEW` | Dew/frost point at 2 m | °C |
| `TS` | Earth skin temperature | °C |
| `WD2M` | Wind direction at 2 m | degrees |
| `WS2M` | Wind speed at 2 m | m/s |

> **Note:** If the Excel file is not found, the script automatically creates an embedded dataset from the values reported in the manuscript (Table S1).

## 🛠️ Requirements

- **R version 4.4.2** or higher
- Required packages (auto-installed if missing):
  - `randomForest` - Random Forest algorithm
  - `readxl` - Excel file import
  - `dplyr` - Data manipulation
  - `caret` - Cross-validation
  - `ggplot2` - Visualization
  - `tidyr` - Data reshaping
  - `patchwork` - Figure combination
  - `corrplot` - Correlation matrices
  - `ggcorrplot` - Enhanced correlation plots
  - `MVN` - Multivariate normality tests
  - `nortest` - Normality tests
  - `psych` - Descriptive statistics
  - `knitr` - Table formatting
  - `kableExtra` - HTML table export

## 🚀 Usage

### Step 1: Clone the repository

```bash
git clone https://github.com/your-username/random-forest-pm25-morocco.git
cd random-forest-pm25-morocco