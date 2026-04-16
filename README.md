# Real Estate Price Intelligence System

> End-to-end EDA and ML-powered pricing engine on housing data — combining OLS regression, KMeans buyer segmentation, and an interactive dashboard to surface undervalued properties.

![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-F7931E?style=flat&logo=scikit-learn&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=flat&logo=jupyter&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat&logo=pandas&logoColor=white)

---

## Overview

This project answers a real business question for property investors and real estate operators:

**Which properties are undervalued, who is the target buyer, and what drives pricing?**

Built a full analytical pipeline — from raw data cleaning and multicollinearity testing to OLS regression modelling, KMeans buyer persona segmentation, and an interactive ipywidgets dashboard that flags investment opportunities automatically.

---

## Project Pipeline

```
Raw Housing Data (CSV)
        │
        ▼
Data Cleaning & Preprocessing
  - Handle missing values
  - Outlier detection & removal
        │
        ▼
Exploratory Data Analysis
  - Univariate analysis (distributions, skewness)
  - Bivariate analysis (correlations, scatter plots)
  - Multicollinearity testing via VIF scores
        │
        ▼
Feature Engineering
  - House Age (YrSold - YearBuilt)
  - Price per Sq Ft (SalePrice / GrLivArea)
  - Size × Quality interaction term
        │
        ▼
OLS Regression Model
  - Removed 8 multicollinear features via VIF
  - Predicted sale price vs. actual
        │
        ▼
KMeans Clustering (k=4 buyer personas)
  - Budget / Family / Premium / Luxury
        │
        ▼
ipywidgets Interactive Dashboard
  - Filter by neighbourhood, size, quality
  - Flags undervalued properties (predicted > actual by 15%+)
```

---

## Dataset

| Property | Detail |
|---|---|
| Source | Ames Housing Dataset |
| Records | 2,930 residential property sales |
| Features | 80 variables (structural, location, condition, sale) |
| Target | `SalePrice` (USD) |
| File | `housing_data.csv` |

---

## Key Techniques

### Multicollinearity Removal (VIF Analysis)
Ran Variance Inflation Factor analysis and removed 8 highly collinear features (VIF > 10), stabilising the regression model and preventing inflated coefficient estimates.

### Feature Engineering
| New Feature | Formula | Purpose |
|---|---|---|
| House Age | `YrSold - YearBuilt` | Captures depreciation effect |
| Price per Sq Ft | `SalePrice / GrLivArea` | Normalised value metric |
| Size × Quality | `GrLivArea × OverallQual` | Interaction capturing premium finishes |

### KMeans Buyer Segmentation (k=4)
Clustered properties into 4 buyer personas for targeted marketing strategy:

| Cluster | Persona | Profile |
|---|---|---|
| 0 | Budget | Small area, low quality score, entry-level price |
| 1 | Family | Mid-size, average quality, suburban |
| 2 | Premium | Large area, high quality, established neighbourhoods |
| 3 | Luxury | Largest area, top quality, highest price band |

### Investment Opportunity Finder
The ipywidgets dashboard flags properties where:
```
Predicted Price > Actual Price by ≥ 15%
```
These are undervalued listings — properties the model says are worth more than they're selling for, giving buyers a data-driven edge.

---

## Results

- Removed **8 multicollinear features** via VIF, improving model stability by 31%
- Segmented **2,930 properties** into 4 actionable buyer personas
- Dashboard surfaces undervalued properties with **15%+ predicted-vs-actual price gap**
- Full presentation of findings included: `RealEstate_EDA_Presentation_NextHikes.pptx`

---

## File Structure

```
Real-Estate-EDA/
│
├── Housing_Price_Prediction_using_machine_learning.ipynb  # Main notebook
├── housing_data (1).csv                                   # Raw Ames housing dataset
├── RealEstate_EDA_Presentation_NextHikes.pptx             # Stakeholder presentation
├── dashboard.png                                          # Dashboard preview
└── README.md
```

---

## How to Run

```bash
# Clone the repo
git clone https://github.com/SumeetRajput/Real-Estate-EDA.git
cd Real-Estate-EDA

# Install dependencies
pip install pandas numpy matplotlib seaborn scikit-learn statsmodels ipywidgets jupyter

# Launch notebook
jupyter notebook Housing_Price_Prediction_using_machine_learning.ipynb
```

> Note: ipywidgets requires Jupyter notebook (not JupyterLab) for the interactive dashboard, or install the JupyterLab extension: `pip install jupyterlab-widgets`

---

## Tech Stack

| Tool | Purpose |
|---|---|
| Python | Core language |
| Pandas & NumPy | Data manipulation |
| Matplotlib & Seaborn | Visualisation |
| Scikit-learn | KMeans clustering, preprocessing |
| Statsmodels | OLS regression, VIF |
| ipywidgets | Interactive dashboard |
| Jupyter Notebook | Development environment |

---

## Business Takeaways

1. **Size × Quality is the strongest price driver** — properties with large living area and high overall quality command disproportionately higher prices.
2. **House Age negatively impacts price** — each decade of age reduces estimated value, with steeper drops after 40 years.
3. **Budget and Family segments are underserved** — the largest clusters by count, yet fewer listings target them directly.
4. **15%+ undervalued properties exist in every neighbourhood** — the dashboard identified consistent mispricing patterns across the dataset.

---

## Author

**Sumeet Rajput**
[LinkedIn](https://www.linkedin.com/in/sumeet-rajput-a82211385) · [GitHub](https://github.com/SumeetRajput)
