# Data Quality Assurance: Hospitality Booking Data 🧹

**Objective:** To perform rigorous structural and logical data cleaning on a raw, 119k+ row hospitality dataset to prepare it for predictive machine learning models. 

Businesses waste thousands of dollars feeding bad data into algorithms. This project demonstrates a "Data QA" approach—treating raw datasets like software that needs to be tested, debugged, and validated.

## 🛠️ The QA Methodology

### 1. Structural Validation (Missing Data)
* **Diagnosis:** Conducted initial smoke tests to identify null values across 32 variables.
* **Resolution:** * Dropped the `company` column due to a 94% null rate.
  * Imputed missing `agent` IDs with `0` (indicating direct bookings).
  * Standardized missing `country` origins as `Unknown`.

### 2. Business Logic Validation (Logical Bugs)
Data can be structurally sound but logically broken. I wrote test scripts to identify bookings that made no physical sense:
* **Ghost Bookings Identified:** Found and purged bookings containing 0 adults, 0 children, and 0 babies (often miscategorized corporate room blocks).
* **Zero-Night Stays Purged:** Removed bookings where the total duration of the stay was 0 nights.
* **Total Illogical Rows Removed:** 825

## 📊 Final Output
* **Initial State:** 119,390 rows / 32 columns
* **Final Pristine State:** 118,565 rows / 33 columns
* **Environment:** Python (Pandas), executed in Google Colab.

You can view the full QA testing script and methodology in the Jupyter Notebook above.
