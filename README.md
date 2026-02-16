# Financial Technology ELT Pipeline
Domain: Digital Payments

## Project Overview

This project implements a modular ELT (Extract, Load, Transform) pipeline within the Financial Technology domain, focusing on digital payments. The pipeline integrates heterogeneous data sources including fintech news articles, transactional payment data and stock market time-series data.

The objective is to demonstrate real-world data engineering practices including secure API authentication, modular code structure, multi-format data storage, and exploratory analysis.

---

## Data Sources

1. News API
   - Purpose: Extract fintech and digital payment-related news articles.
   - Data Type: Semi-structured JSON.
   - Parameters Used:
     - Query: "digital payments OR fintech OR mobile payments"
     - Language: English
     - Sort by: Published date
     - Page size: 50 articles

2. Kaggle Dataset (PaySim)
   - Dataset: Mobile money transaction simulation dataset.
   - Data Type: Structured CSV.
   - Contains transaction types, balances, fraud indicators.

3. Yahoo Finance (yfinance)
   - Companies: PayPal (PYPL), Visa (V), Mastercard (MA)
   - Data Type: Structured time-series data.
   - Date Range: 2020–2025
   - Variables: Open, Close, High, Low, Volume

---

## Project Structure

data/
│
├── raw/          → Original extracted data
├── processed/    → Converted CSV and JSON files
└── cleaned/      → Cleaned datasets for analysis

notebook/
└── ELT_pipeline.ipynb

README.md
Report.pdf
Answerspart1and2.pdf
---

## Installation Requirements

Run the following in Google Colab:

pip install yfinance kaggle python-dotenv requests seaborn matplotlib

---

## API Configuration

Before running the pipeline, set environment variables in Colab:

import os

os.environ["NEWS_API_KEY"] = "4bcf286a8f3d4a209d8a2b090298ccd7"
os.environ["KAGGLE_USERNAME"] = "mahnoorimran2026"
os.environ["KAGGLE_KEY"] = "KGAT_63fe84f5f689a013443f1de63d805743"

---

## How to Run the Pipeline

1. Install required libraries.
2. Set API environment variables.
3. Run the notebook cells sequentially.
4. Execute the run_pipeline() function.
5. Processed datasets will be stored in data/processed/.
6. Cleaned datasets will be stored in data/cleaned/.

---

## Data Cleaning and Transformation

The following transformations were applied:

- Duplicate records removed.
- Missing values handled using fillna() and forward filling for time-series data.
- Date columns standardized using datetime conversion.
- Categorical variables converted to appropriate types.

---

## Assumptions Made

- News API free tier limits were sufficient for extraction.
- Kaggle PaySim dataset represents realistic digital transaction behavior.
- Stock prices of PayPal, Visa, and Mastercard reflect trends in digital payment adoption.
- Missing time-series values represent non-trading days and were forward-filled.
- Fraud patterns in the PaySim dataset can approximate real-world financial fraud behavior.

---

## Potential AI Applications

The engineered datasets could support:
- Fraud detection models
- Financial trend forecasting
- Risk scoring systems
- Payment behavior analysis

---

Name: Mahnoor Imran
ID: 25280082

