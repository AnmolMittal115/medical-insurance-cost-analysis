# 💳 Medical Insurance Cost Analysis

> **A visual, notebook-based exploration of what moves medical insurance charges.**

This project uses Python to explore a classic insurance dataset and prepare its features for analysis. Follow the charts from the first look at the data through cleaning, feature engineering, scaling, and statistical feature checks.

![Python](https://img.shields.io/badge/Python-3.10%2B-3776AB?logo=python&logoColor=white)
![Jupyter](https://img.shields.io/badge/Notebook-Jupyter-F37626?logo=jupyter&logoColor=white)
![Focus](https://img.shields.io/badge/Focus-Exploratory%20Data%20Analysis-7C3AED)

---

## ✨ Project snapshot

| | |
|---|---|
| **Question** | How do age, BMI, smoking status, family size, sex, and region relate to insurance charges? |
| **Data** | 1,338 rows · 7 columns |
| **Target** | `charges` — a continuous cost measure |
| **Tools** | Python · pandas · seaborn · Matplotlib · SciPy · scikit-learn |
| **Best place to start** | [Open the analysis notebook](medical_insurance_cost_analysis.ipynb) |

## 📊 Take a visual tour

The charts below are exported from the notebook’s saved outputs, so they’re easy to preview without running any code.

| Insurance charge distribution | Charges by smoking status |
|---|---|
| ![Distribution of insurance charges](images/charges_distribution.png) | ![Count of records by smoking status](images/smoker_counts.png) |

| Numeric feature correlations | Charge outliers and spread |
|---|---|
| ![Correlation heatmap for numeric variables](images/numeric_correlation_heatmap.png) | ![Boxplot of insurance charges](images/charges_boxplot.png) |

| BMI distribution before feature engineering | BMI distribution after duplicate removal |
|---|---|
| ![BMI distribution before cleaning](images/bmi_distribution.png) | ![BMI distribution after duplicate removal](images/bmi_distribution_after_cleaning.png) |

<details>
<summary><strong>See all saved notebook charts</strong></summary>

### Distributions

| Age | BMI | Children | Charges |
|---|---|---|---|
| ![Age distribution](images/age_distribution.png) | ![BMI distribution](images/bmi_distribution.png) | ![Children distribution](images/children_distribution.png) | ![Charges distribution](images/charges_distribution.png) |

### Category counts

| Sex | Smoker | Children | Region |
|---|---|---|---|
| ![Sex counts](images/sex_counts.png) | ![Smoker counts](images/smoker_counts.png) | ![Children counts](images/children_counts.png) | ![Region counts](images/region_counts.png) |

### Boxplots

| Age | BMI | Children | Charges |
|---|---|---|---|
| ![Age boxplot](images/age_boxplot.png) | ![BMI boxplot](images/bmi_boxplot.png) | ![Children boxplot](images/children_boxplot.png) | ![Charges boxplot](images/charges_boxplot.png) |

</details>

## 🧭 How the analysis flows

```mermaid
flowchart LR
    A[insurance.csv<br/>1,338 records] --> B[Explore<br/>summaries · charts · data quality]
    B --> C[Clean<br/>remove duplicate · check missing values]
    C --> D[Prepare categories<br/>binary maps · region one-hot encoding]
    D --> E[Engineer features<br/>BMI groups]
    E --> F[Scale numeric inputs]
    F --> G[Study relationships<br/>correlation · chi-square]
    G --> H[Analysis notebook]
```

## 🔎 What stood out

- The source file contains **1,338 records** and has no missing values; the notebook removes one duplicate during cleaning.
- The charge histogram has a long right tail: most observations are lower, with fewer very high charges.
- In the notebook’s Pearson analysis, smoking status has the strongest listed association with charges (**r ≈ 0.787**), followed by age (**r ≈ 0.298**) and BMI (**r ≈ 0.198**).
- These are exploratory relationships in this dataset. They do not show that a feature causes higher charges.

## 🧪 What’s inside the notebook

The notebook walks through:

1. Dataset shape, types, summary statistics, and missing-value checks
2. Histograms, category counts, boxplots, and a numeric correlation heatmap
3. Duplicate removal and categorical encoding
4. BMI grouping and one-hot encoding
5. Standard scaling for selected numeric features
6. Pearson correlation and chi-square feature exploration

The project is an **EDA and feature-preparation study**. It focuses on understanding the data and does not present a trained prediction model or test-set score.

> **Preprocessing note:** Boolean one-hot columns are converted to 0/1 flags; continuous BMI and charge values retain their decimal precision.

## 🚀 Run it yourself

Clone or download this repository, then from its root:

```bash
python -m venv .venv
```

Activate the environment and install the packages:

```bash
python -m pip install -r requirements.txt
```

Launch the notebook:

```bash
jupyter notebook medical_insurance_cost_analysis.ipynb
```

The CSV is kept beside the notebook, so its existing `pd.read_csv("insurance.csv")` cell works when Jupyter starts from the repository root.

## 🗂️ Repository map

```text
.
├── images/                              # chart exports shown above
├── insurance.csv                        # analysis dataset
├── medical_insurance_cost_analysis.ipynb # full notebook and saved outputs
├── requirements.txt
└── README.md
```

## 📚 Dataset

The data matches the [Medical Cost Personal Datasets on Kaggle](https://www.kaggle.com/datasets/mirichoi0218/insurance). It contains age, sex, BMI, number of dependents, smoking status, region, and individual insurance charges.
