# 📊 DA-and-ML-PJT1: Data Analytics and Machine Learning Project

> **Course:** Data Analytics & Machine Learning (or IT Project Management)  
> **University:** Ajou University in Tashkent (AUT)  

---

## 👥 1. Team Information

**Team Name:** `EST`

| Role | Name | Student ID | Group |
| :--- | :--- | :--- | :--- |
| **Leader** | Temur Shirinboyev | 202490298 | I-24A |
| **Member** | Suxrob Hazratqulov | 202490129 | I-24C |
| **Member** | Elbek Ismoilov | 202490143 | I-24C |
| **Member** | Behruz Abdullayev | 202490012 | I-24C | *(Note: Confirm exact group if different)* |

---

## 📌 2. Project Title & Overview

**Project Title:** Online Retail Customer Segmentation & Sales Analysis

This project focuses on analyzing online retail sales data, studying customer purchasing behavior, segmenting customers using Machine Learning models (K-Means), and generating actionable business insights based on data analysis.

---

## 📊 3. Dataset Information

* **Dataset Title:** Online Retail II
* **Source Website:** [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/index.php)
* **Description:** A transactional dataset containing all transactions occurring between 2009 and 2011 for a UK-based and registered non-store online retail.
* **Why Selected:** It provides real-world transactional data perfect for practicing data cleaning, EDA, and implementing Recency, Frequency, Monetary (RFM) analysis and clustering.
* **Size:** Contains over 500,000 rows and 8 columns (InvoiceNo, StockCode, Description, Quantity, InvoiceDate, UnitPrice, CustomerID, Country).

---

## 🎯 4. Project Objectives

* **Problem Statement:** How can an online retail business identify its most valuable customers and tailor marketing strategies to different customer segments?
* **Research Questions:**
  1. What are the overall sales trends over time and across different countries?
  2. Who are the top-selling products and what generates the most revenue?
  3. How can we segment customers based on their purchasing behavior?
* **Expected Insights:** Identification of "Champions," "Loyal," and "At-Risk" customer segments to optimize marketing and operational strategies.

---

## 🛠️ 5. Data Preparation (Using Pandas)

Data preparation and cleaning steps performed to ensure high data quality:

```python
import pandas as pd
import numpy as np

# Load dataset
df = pd.read_excel('online_retail_II.xlsx')

# 1. Handle missing values (NaN)
df.dropna(subset=['Customer ID', 'Description'], inplace=True)

# 2. Remove duplicates
df.drop_duplicates(inplace=True)

# 3. Filter negative values (Returns/Cancellations)
df = df[(df['Quantity'] > 0) & (df['Price'] > 0)]

# 4. Convert InvoiceDate to datetime
df['InvoiceDate'] = pd.to_datetime(df['InvoiceDate'])
