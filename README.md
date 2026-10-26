# 📦 QuickCart – Warehouse Inventory Stockout Risk Prediction

### Machine Learning for Inventory Risk Classification

## 📌 Project Overview

**QuickCart – Warehouse Inventory Stockout Risk Prediction** is a machine learning project designed to identify products that may run out of stock before the next supplier delivery arrives.

The project analyzes inventory data across multiple stores, products, suppliers, and dates to classify inventory into three risk categories: **Safe, At-Risk, and Imminent**.

Using Python, data preprocessing, feature engineering, and supervised machine learning classification models, this project explores how predictive analytics can support inventory planning, reduce stockout risks, and improve replenishment decisions.

## 🎯 Project Objectives

- Predict inventory stockout risk for individual products across stores and dates.
- Analyze inventory levels, sales velocity, and supplier lead times.
- Investigate the impact of festival demand and promotional events on inventory.
- Clean and combine multiple datasets into a modeling dataset.
- Engineer meaningful features for machine learning.
- Compare classification models using appropriate evaluation metrics.
- Identify imminent stockout risks to support timely replenishment decisions.

## 🛠️ Technologies Used

- **Programming Language:** Python
- **Environment:** Jupyter Notebook / Google Colab
- **Data Manipulation:** Pandas and NumPy
- **Data Visualization:** Matplotlib and Seaborn
- **Machine Learning:** Scikit-learn
- **Classification Models:** Logistic Regression, Random Forest, and Gradient Boosting
- **Evaluation Metrics:** Accuracy, Recall, Macro F1-score, Classification Report, and Confusion Matrix

## 📊 Dataset Information

The project uses synthetic inventory data for a fictional quick-commerce company named QuickCart.

- **Inventory Records:** 21,600
- **Stores:** 12
- **Product SKUs:** 60
- **Suppliers:** 15
- **Product Categories:** 8
- **Observation Period:** October 1–30, 2026
- **Target Variable:** `stockout_risk`
- **Prediction Classes:** Safe, At-Risk, and Imminent

### Dataset Files

The dataset ZIP file contains the CSV files used in the project.

| Dataset                    | Description                                                     |
| -------------------------- | --------------------------------------------------------------- |
| `dim_stores.csv`           | Store information, locations, sizes, and baseline demand        |
| `dim_skus.csv`             | Product details, categories, prices, shelf life, and popularity |
| `dim_suppliers.csv`        | Supplier information, reliability scores, and lead times        |
| `dim_events.csv`           | Festival and promotional event calendar                         |
| `fact_inventory_daily.csv` | Daily inventory records and stockout risk labels                |

### Target Variable

The `stockout_risk` variable classifies inventory records into three categories:

- **Safe:** Lower immediate stockout risk.
- **At-Risk:** Inventory requires monitoring and may need replenishment.
- **Imminent:** Higher-priority stockout risk requiring attention.

The classification labels represent the categories defined in the synthetic dataset.

## 🔍 Project Workflow

### 1. Data Loading and Validation

- Loaded the CSV datasets using Pandas.
- Checked dataset dimensions, row counts, and date ranges.
- Examined the distribution of stockout risk classes.
- Validated relationships between inventory, store, product, supplier, and event data.

### 2. Data Cleaning and Preprocessing

- Standardized inconsistent city-name capitalization.
- Handled missing supplier reliability values.
- Configured missing-value markers while reading CSV files.
- Checked relationships between suppliers and products.
- Verified that joining datasets preserved the expected inventory records.

### 3. Exploratory Data Analysis

Investigated relationships between stockout risk and important business factors, including:

- Festival and promotional demand.
- Supplier reliability.
- Perishable and non-perishable products.
- Inventory levels and sales velocity.

Data visualizations were used to explore patterns and communicate findings.

### 4. Feature Engineering

Created additional features to help represent inventory risk, including:

- `reorder_gap` — difference between the reorder point and closing stock.
- `days_of_cover_ratio` — stock coverage relative to expected supplier lead time.
- `supplier_reliability_clean` — cleaned supplier reliability values.
- `is_recent_reorder` — indicator of a recent reorder within the same store-product combination.
- `day_of_month` — calendar day of the month.
- `days_since_festival_start` — number of days relative to the festival period's start.

Categorical variables were also converted into numerical features for model training.

### 5. Machine Learning Models

The project compares four classification approaches:

1. **Dummy Classifier:** Establishes a baseline using a simple prediction strategy.
2. **Logistic Regression:** Provides a classification model that is relatively easy to interpret.
3. **Random Forest:** Uses an ensemble of decision trees to model potentially nonlinear relationships.
4. **Gradient Boosting:** Combines sequentially trained models to improve classification performance.

A time-based train/test split was used, with training data from October 1–23 and testing data from October 24–30.

### 6. Model Evaluation

The models are evaluated using:

- Accuracy
- Recall for the Imminent class
- Macro F1-score
- Classification reports
- Confusion matrices

**Why Imminent recall matters:** Missing a high-risk inventory record can lead to stockouts and lost sales. Therefore, evaluating how effectively a model identifies imminent stockout risk is important alongside overall accuracy.

### 7. Feature Importance and Interpretation

- Examined feature importance from Random Forest and Gradient Boosting.
- Inspected Logistic Regression coefficients for the Imminent class.
- Compared model behavior to understand the contribution of different features.
- Performed an additional Random Forest evaluation after removing days-of-cover features to investigate possible target leakage.

## 💡 Business Questions

This project explores questions such as:

- Does festival demand increase the likelihood of imminent stockouts?
- How does supplier reliability relate to inventory risk?
- Are perishable products more vulnerable to stockouts?
- Which inventory and demand-related features help predict stockout risk?
- Which classification model best identifies imminent stockouts?
- How can inventory teams prioritize products requiring replenishment?

## 📈 Potential Business Benefits

- Earlier identification of potential stockouts.
- Better-informed inventory replenishment planning.
- Improved understanding of supplier reliability.
- Greater awareness of seasonal and festival-driven demand.
- Reduced risk of lost sales due to inventory shortages.
- Data-driven support for inventory management decisions.

These are potential benefits; actual operational improvements would need to be validated using real business data.

## 📁 Repository Structure

```text
QuickCart-Stockout-Risk-Prediction/
│
├── README.md
├── quickcart.ipynb
└── dim_events.zip
```

### File Descriptions

- **`README.md`** — Project overview, dataset information, methodology, and execution instructions.
- **`quickcart.ipynb`** — Jupyter Notebook containing the data analysis, feature engineering, model training, and evaluation workflow.
- **`dim_events.zip`** — Compressed dataset containing the CSV files required for the project.

## ▶️ How to Run the Project

### Prerequisites

- Python 3.x
- Jupyter Notebook or Google Colab
- Required Python libraries: Pandas, NumPy, Matplotlib, Seaborn, and Scikit-learn

### Execution Steps

1. Clone or download this GitHub repository.
2. Download `dim_events.zip`.
3. Extract the ZIP file to access the five CSV datasets.
4. Upload `quickcart.ipynb` and the extracted CSV files to Google Colab, or place them in the appropriate local working directory.
5. Ensure the CSV file paths in the notebook match their actual locations.
6. Install any missing Python libraries if necessary.
7. Open `quickcart.ipynb`.
8. Run the notebook cells in order.
9. Review the exploratory analysis, classification results, evaluation metrics, and feature importance outputs.

**Important:** The notebook must be able to access all five CSV files. If it uses a specific folder path, update that path to match your environment before running the cells.

## 📚 Skills Demonstrated

- Python programming
- Data cleaning and preprocessing
- Exploratory data analysis
- Dataset integration and validation
- Feature engineering
- Supervised machine learning
- Multiclass classification
- Model evaluation and comparison
- Feature importance and model interpretation
- Business-focused predictive analytics

## 👩‍💻 Author

**Srusti Shree K H**

## 📑 Project Information

- **Project Name:** QuickCart – Warehouse Inventory Stockout Risk Prediction
- **Project Type:** Minor Project
- **Domain:** Data Analytics and Machine Learning
- **Business Domain:** Retail Analytics, Quick Commerce, and Inventory Management
- **Programming Language:** Python
- **Core Technologies:** Pandas, NumPy, Scikit-learn, Matplotlib, and Seaborn
- **Dataset Size:** 21,600 inventory records
- **Stores Analyzed:** 12
- **Product SKUs:** 60
- **Suppliers:** 15
- **Prediction Task:** Three-class stockout risk classification
- **Target Classes:** Safe, At-Risk, and Imminent
- **Purpose:** Academic learning and practical application of machine learning for inventory risk prediction.

---

*This project was developed for educational purposes using synthetic QuickCart inventory data. It demonstrates how data analytics and machine learning can be applied to inventory risk classification and replenishment planning.*
