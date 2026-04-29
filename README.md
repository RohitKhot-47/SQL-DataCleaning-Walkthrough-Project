# 🧹 SQL Data Cleaning — Tech Layoffs Dataset

A focused SQL data cleaning project built while learning SQL from scratch. Followed Alex The Analyst's walkthrough as a guide but wrote every query independently — making my own mistakes, debugging them, and understanding the logic rather than copy-pasting.

The goal was to solidify core data cleaning techniques through real practice before moving into independent analysis.

Dataset source: [Kaggle — Layoffs 2022](https://www.kaggle.com/datasets/swaptr/layoffs-2022)

---

## 🛠️ Tools Used

- **MySQL** — all queries written and executed in MySQL Workbench
- **Dataset** — 2022 global tech layoffs (company, location, industry, layoff numbers, funding stage)

---

## 🔍 What This Project Covers

### 1. Removing Duplicates
- Created a staging table to preserve raw data
- Used `ROW_NUMBER()` with `PARTITION BY` to identify exact duplicate rows
- Deleted duplicates safely without touching the original table

### 2. Standardizing Data
- Trimmed extra whitespace from company names using `TRIM()`
- Standardized inconsistent industry labels (e.g. `Crypto`, `Crypto Currency`, `CryptoCurrency` → all unified to `Crypto`)
- Fixed trailing punctuation in country names using `TRIM(TRAILING '.' FROM country)`
- Converted date column from text format to proper `DATE` type using `STR_TO_DATE()`

### 3. Handling Null Values
- Identified null and blank industry fields
- Used a self `JOIN` to populate missing industry values where another row for the same company had the data
- Removed rows where both `total_laid_off` and `percentage_laid_off` were null — unusable for analysis

---

## 📂 Files

| File | What it does |
|------|-------------|
| `DELETING_DUPLICATES-PROJECT-01.sql` | Duplicate detection and removal |
| `STANDERDAIZATION.sql` | Text cleaning and date formatting |
| `NULL_VALUES.sql` | Null handling and row removal |

---

## 💡 Key Techniques Used

`ROW_NUMBER()` · `PARTITION BY` · `CTEs` · `Self JOIN` · `STR_TO_DATE()` · `TRIM()` · `ALTER TABLE` · `UPDATE` · `DELETE`

---
