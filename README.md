# Data Cleaning & Preprocessing using Pandas

## Project Overview

This project demonstrates an end-to-end data cleaning and preprocessing workflow using **Python and Pandas** on a real-world e-commerce transaction dataset.

The objective was to inspect the raw dataset, identify data-quality issues, validate the data, perform preprocessing, engineer useful business features, and export a clean standardized dataset for further analysis.

---

## Dataset

**Dataset:** Maven Fuzzy Factory E-Commerce Orders

The raw `orders.csv` dataset contains **32,313 transaction records** and **8 original columns**.

### Original Columns

- `order_id`
- `created_at`
- `website_session_id`
- `user_id`
- `primary_product_id`
- `items_purchased`
- `price_usd`
- `cogs_usd`

---

## Objectives

The project focuses on:

- Loading and inspecting raw business data using Pandas
- Checking missing values
- Identifying duplicate records
- Validating data types
- Converting date fields into proper datetime format
- Detecting potential outliers using the IQR method
- Validating business-critical numeric values
- Extracting Year and Month features
- Calculating revenue
- Calculating total cost
- Calculating profit
- Calculating profit margin
- Exporting the final cleaned dataset as CSV

---

## Data Quality Assessment

### Before Cleaning

| Quality Check | Result |
|---|---:|
| Total Rows | 32,313 |
| Total Columns | 8 |
| Missing Values | 0 |
| Duplicate Rows | 0 |
| Invalid Dates | 0 |

The `created_at` column was initially stored as an object/string datatype and required conversion to datetime.

Potential outliers were identified using the **Interquartile Range (IQR)** method. Further validation showed that the detected values were valid business observations rather than impossible values.

---

## Data Cleaning Performed

The following preprocessing steps were implemented:

1. Removed exact duplicate records.
2. Converted `created_at` into a proper datetime datatype.
3. Converted numeric fields into appropriate numeric datatypes.
4. Removed records with invalid essential values.
5. Validated that:
   - `items_purchased > 0`
   - `price_usd > 0`
   - `cogs_usd > 0`
6. Verified missing values after cleaning.
7. Verified duplicate records after cleaning.

### Cleaning Result

| Metric | Before Cleaning | After Cleaning |
|---|---:|---:|
| Rows | 32,313 | 32,313 |
| Columns | 8 | 15 |
| Missing Values | 0 | 0 |
| Duplicate Rows | 0 | 0 |

No rows were removed because the dataset did not contain missing, duplicate, or invalid business-critical records.

---

## Feature Engineering

Seven new analytical features were created:

### 1. Year

Extracted the year from `created_at`.

### 2. Month

Extracted the numerical month from `created_at`.

### 3. Month Name

Created a readable month name such as March.

### 4. Revenue

```text
Revenue = Items Purchased × Price USD
```

### 5. Total Cost

```text
Total Cost = Items Purchased × COGS USD
```

### 6. Profit

```text
Profit = Revenue − Total Cost
```

### 7. Profit Margin

```text
Profit Margin (%) = (Profit / Revenue) × 100
```

---

## Final Dataset

The cleaned dataset contains:

- **32,313 rows**
- **15 columns**
- **0 missing values**
- **0 duplicate records**

The final dataset is available as:

`clean_dataset.csv`

---

## Project Structure

```text
task-03-data-cleaning-preprocessing/
│
├── Task_03_Data_Cleaning_Preprocessing.ipynb
├── clean_dataset.csv
└── README.md
```

---

## Tools & Technologies

- Python
- Pandas
- NumPy
- Google Colab
- Jupyter Notebook
- GitHub
- CSV

---

## Key Outcomes

- Successfully processed a dataset containing more than **32K transaction records**
- Validated data completeness and uniqueness
- Standardized date and numeric datatypes
- Performed outlier analysis using IQR
- Validated business-critical numerical values
- Created revenue, cost, profit, and profit-margin features
- Produced a clean standardized CSV dataset ready for further analysis

---

## Files

### Jupyter Notebook

`Task_03_Data_Cleaning_Preprocessing.ipynb`

Contains the complete data loading, profiling, cleaning, validation, preprocessing, and feature engineering workflow.

### Clean Dataset

`clean_dataset.csv`

Contains the final standardized dataset after preprocessing and feature engineering.

---

## Author

**Gautam Kumar Dutta**

B.Tech – Computer Science Engineering
