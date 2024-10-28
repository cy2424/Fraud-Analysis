# Fraud Detection Analysis using PySpark

This repository contains a Jupyter notebook designed to analyze a dataset of credit card transactions, with a focus on detecting fraudulent activities. The analysis leverages PySpark to handle data transformations and visualizations, addressing data cleaning, PII handling, and timestamp conversion, while also providing insights through meaningful visualizations.

## Table of Contents
- [Objective](#objective)
- [Dataset Information](#dataset-information)
- [Data Transformation and Cleaning](#data-transformation-and-cleaning)
- [Handling PII](#handling-pii)
- [Visualization and Analysis](#visualization-and-analysis)
- [Results](#results)
- [Project Structure](#project-structure)

## Objective
The primary goal of this project is to:
- **Read and Transform the Dataset:** Use PySpark to load and process the data, ensuring cleanliness and readiness for analysis.
- **Analyze and Visualize Data:** Generate insights into transaction patterns and identify potential fraud cases through creative visualizations.
- **PII Management and Data Quality:** Apply effective techniques for handling PII, timestamp formatting, and data quality assurance.

## Dataset Information
The dataset is sourced from Kaggle and includes details of credit card transactions with the following relevant fields:
- Transaction details (e.g., transaction time, amount, merchant info)
- Personal details of the card owner (e.g., name, address, gender)
- Fraud indicators (flag for fraudulent transactions)

Given the messy nature of this data, substantial data cleaning is required.

## Data Transformation and Cleaning

### Key Transformation Steps
1. **Flatten JSON:** Convert JSON data into a tabular format to include the following fields:
   - `Unnamed: 0`, `trans_date_trans_time`, `cc_num`, `merchant`, `category`, `amt`, `first`, `last`, `gender`, `street`, `city`, `state`, `zip`, `lat`, `long`, `city_pop`, `job`, `dob`, `trans_num`, `merch_lat`, `merch_long`, `is_fraud`, `merch_zipcode`, `merch_last_update_time`, `merch_eff_time`, `cc_bic`
   
2. **Handle Dirty Data:** Identify and clean any anomalies in fields such as `person_name`, `address`, and transaction details.

3. **PII Management:** Encrypt and mask personally identifiable information, particularly credit card numbers, to ensure data privacy.

4. **Timestamp Conversion:** Convert all time-related columns to a human-readable format in UTC+8 timezone (e.g., `YYYY-MM-DD HH:MM:SS.SSSSSS Z`).

5. **Name Extraction:** Parse `person_name` field into `first` and `last` name columns, handling irregularities based on common patterns.

### Handling PII
In accordance with data privacy standards, sensitive information such as credit card numbers (`cc_num`) is encrypted. Detailed markdown explanations within the notebook describe the approach to ensure that personally identifiable information (PII) is safeguarded throughout the analysis.

## Visualization and Analysis

The notebook includes various visualizations to extract insights from the data:
- **Transaction Trends:** Analyze transaction volume over time and detect any anomalous spikes or patterns.
- **Fraud Pattern Analysis:** Visualize trends specific to fraudulent transactions, such as distribution by category or location.
- **Geospatial Analysis:** Utilize latitude and longitude data to explore merchant and transaction locations.
- **Additional Insights:** Integrate additional datasets (e.g., city demographics) for more contextual analysis.

## Results
The analysis reveals trends in transaction behavior and provides insights into possible fraud indicators, such as unusual spending patterns or high-risk merchant categories.

