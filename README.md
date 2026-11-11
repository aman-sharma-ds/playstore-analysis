# playstore-analysis
# Google Play Store Apps: Exploratory Data Analysis

An end-to-end exploratory data analysis of ~10,800 Google Play Store apps, covering data cleaning, univariate and bivariate analysis, and key insights about categories, ratings, pricing and installs.

## Table of Contents
- [Project Overview](#project-overview)
- [Dataset](#dataset)
- [Tech Stack](#tech-stack)
- [Data Cleaning](#data-cleaning)
- [Analysis & Key Findings](#analysis--key-findings)
- [Project Structure](#project-structure)
## Project Overview

The goal of this project is to understand what the Android app market looks like: which categories dominate, how apps are rated, how free and paid apps differ, and how installs relate to user engagement (reviews).

## Dataset

- **Source:** Google Play Store Apps dataset (Kaggle), file `googleplaystore.csv`
- **Size:** 10,841 rows × 13 columns
- **Columns:** `App`, `Category`, `Rating`, `Reviews`, `Size`, `Installs`, `Type`, `Price`, `Content Rating`, `Genres`, `Last Updated`, `Current Ver`, `Android Ver`

## Tech Stack

Python · Pandas · NumPy · Matplotlib · Seaborn · Jupyter Notebook

## Data Cleaning

The raw data had several quality issues that needed fixing before analysis:

| Issue | Fix |
|---|---|
| One corrupted row with shifted columns (Rating = 19, invalid Category/Type) | Dropped the row |
| `Reviews` stored as text | Converted to numeric |
| `Size` mixed units (`M`, `k`, `Varies with device`) | Converted everything to KB; "Varies with device" set to NaN |
| `Installs` contained `,` and `+` | Stripped symbols and converted to numeric |
| `Price` contained `$` | Stripped symbol and converted to numeric |
| Missing `Type` and `Content Rating` (1 row each) | Dropped those rows |
| Duplicate apps | Removed duplicates by app name, keeping the entry with the most reviews |
| Missing `Rating` (~1,400 apps) | Left as NaN so averages and plots are not distorted by artificial values |

## Project Structure

```
├── data-analysis.ipynb    # Full analysis notebook
├── googleplaystore.csv    # Dataset
└── README.md
```
## Author

**[aman sharma]**
[LinkedIn](https://www.linkedin.com/in/aman-sharma-792052415) · [GitHub](https://github.com/aman-sharma-ds)
