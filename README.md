# Suspicious Web Threat Detection using AWS CloudWatch Logs

This project analyzes web traffic logs and detects suspicious behavior using a mix of **clustering** and **anomaly detection**.

## What it does
- Loads CloudWatch traffic data from `CloudWatch_Traffic_Web_Attack.csv`
- Cleans and selects the key features (bytes, ports, protocol, response codes, rule names, etc.)
- Encodes categorical fields (LabelEncoder) and scales features (StandardScaler)
- Builds:
  - **K-Means (k=3)** to group traffic patterns
  - **Isolation Forest** (contamination=0.1) to flag anomalies
  - **Decision Tree (max_depth=5)** to explain anomaly decisions
- Produces:
  - Distributions (bytes_in/bytes_out)
  - Correlation heatmap
  - Cluster and anomaly scatterplots
  - Summary of anomaly counts
  - Feature importance bar chart
  - Decision tree visualization
  - Classification report and confusion matrix

## Dataset
Place the CSV in the project root:
- `CloudWatch_Traffic_Web_Attack.csv`

## How to run with Google Colab
1. Upload `CloudWatch_Traffic_Web_Attack.csv` to the Colab.
2. Run "all cells".
