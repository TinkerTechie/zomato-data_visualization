# zomato-data_visualization
# Zomato Restaurant Analytics — Data Cleaning & Dashboard

## Overview

This project analyzes restaurant data from the Zomato Bangalore dataset to understand cuisine trends, pricing patterns, service availability, and geographic distribution of restaurants.
The raw dataset contained inconsistent formats, multi-label categorical fields, and textual numeric values, requiring structured preprocessing before analysis.

The objective was to create a clean, standardized dataset suitable for pivot-based dashboard visualization.

---

## Dataset

**Source:** Zomato Bangalore Restaurants Dataset (Kaggle)
**Original Size:** ~51,000 restaurants
**Working Sample:** 10,000 restaurants (randomly sampled)

---

## Data Cleaning & Preprocessing

### 1. Column Selection

Irrelevant identifiers and unstructured text fields were removed:

* url
* phone
* reviews_list
* menu_item

These fields do not support aggregation or analytical comparison.

---

### 2. Rating Cleaning

The `rate` column contained mixed formats such as:

* `4.3/5`
* `NEW`
* `-`
* missing

Processing steps:

* Extracted numeric rating from text
* Treated non-numeric entries as missing
* Replaced missing values using median imputation
* Created `rating_clean`

---

### 3. Cost Cleaning

The `approx_cost(for two people)` column contained comma-separated text values.

Processing steps:

* Removed non-numeric characters
* Converted to numeric format
* Standardized column name to `cost_for_two`

---

### 4. Cuisine Standardization

The `cuisines` field contained multiple cuisines per restaurant.

Processing:

* Extracted primary cuisine (first listed)
* Created `primary_cuisine`

This enables categorical aggregation and comparison.

---

### 5. Restaurant Type Standardization

The `rest_type` field contained multiple types.

Processing:

* Extracted primary restaurant type
* Created `primary_rest_type`

---

### 6. Geographic Standardization

The `location` and `listed_in(city)` fields had inconsistent capitalization and spacing.

Processing:

* Trimmed extra spaces
* Standardized capitalization
* Created `location_clean` and `city_clean`

---

### 7. Final Feature Consolidation

Cleaned columns were converted from formulas to static values.
Original raw columns were removed to eliminate redundancy and ensure analytical clarity.

---

## Final Cleaned Dataset Fields

* name
* address
* online_order
* book_table
* votes
* rating_clean
* cost_for_two
* primary_cuisine
* primary_rest_type
* location_clean
* city_clean
* listed_in(type)

---

## Analysis Objectives

The cleaned dataset enables analysis of:

* Restaurant distribution by location and city
* Cuisine popularity
* Average rating by cuisine and type
* Pricing patterns across cuisines and zones
* Service availability (online order / table booking)
* Restaurant type distribution

---

## Tools Used

* Google Sheets (data cleaning, pivot tables, dashboard)
* Kaggle (dataset source)

---

## Outcome

A fully standardized restaurant dataset suitable for multidimensional analysis and dashboard visualization was created from raw Zomato data through systematic preprocessing and feature engineering.

---

## Author

Zomato Data Analytics Project
Data Visualization & Analytics
