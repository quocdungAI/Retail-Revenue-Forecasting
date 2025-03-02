# Retail-Revenue-Forecasting
Retail Sales Forecasting Based on Time, and Product Categories
# Retail Sales Forecasting for the Vietnamese Market

This project provides a robust forecasting model for retail sales in Vietnam, leveraging time series data and product categories. By combining **Deep Temporal Clustering (DTC)** with **Random Forest**, it addresses the unique challenges of the Vietnamese market, such as distinct consumer behavior and seasonal patterns. The model is trained on data from **January 2009 to August 2024**, covering sectors like trade, tourism, hotels, restaurants, and services.

---

## Table of Contents

- [Introduction](#introduction)
- [Data](#data)
- [Methodology](#methodology)
- [Results](#results)
- [Requirements](#requirements)

---

## Introduction

Accurate retail sales forecasting is vital for optimizing business strategies and inventory management. Traditional models often fail to capture Vietnam-specific dynamics. This project introduces a hybrid approach using DTC to cluster time series patterns and Random Forest to predict sales, improving forecast precision for better decision-making.

---

## Data

The dataset is sourced from [VietstockFinance](https://vietstock.vn/), covering monthly retail sales from **January 2009 to August 2024**. It includes:

- **Total Retail Sales**
- **Trade (Thương nghiệp)**
- **Hotels and Restaurants (Khách sạn nhà hàng)**
- **Tourism (Du lịch)**
- **Services (Dịch vụ)**
- 
## Methodology

The model combines two key techniques:

1. **Deep Temporal Clustering (DTC)**:
   - Uses LSTM layers to extract time series features and capture long-term dependencies.
   - Clusters data into groups with similar temporal patterns.

2. **Random Forest**:
   - Predicts sales using clustered data as features.
   - Excels at handling structured data and non-linear relationships.

### Workflow
- **LSTM**: Models time series patterns.
- **DTC Layer**: Clusters data points.
- **Random Forest**: Enhances predictions with clustering results.

![Model Architecture](![image](https://github.com/user-attachments/assets/8aa33d8f-fe1d-4459-8d74-42337d9c9860)
)

---

## Results

The model significantly improves forecasting accuracy:

### RMSE Comparison
- **Random Forest with K-Means**: 0.0474
- **Random Forest with DTC**: 0.00398

### RMSE by Sector (with DTC)
- **Total Revenue**: 0.00398
- **Trade**: 0.00357
- **Hotels and Restaurants**: 0.00495
- **Tourism**: 0.01618
- **Services**: 0.00783

### Training vs. Testing
- **Training RMSE**: 0.00425
- **Testing RMSE**: 0.00398

### Cluster Insights
- **Stable Clusters**: Trade shows consistent trends.
- **Volatile Clusters**: Tourism and hotels reflect seasonal fluctuations.

### 2025 Total Revenue Forecast
Below are the predicted total revenues for the first eight months of 2025:
- **January**: 146,115
- **February**: 144,105
- **March**: 143,182
- **April**: 142,321
- **May**: 141,670
- **June**: 140,463
- **July**: 140,642
- **August**: 140,607

### Conclusion on Model Comparison
Based on the comparison of average RMSE for K-Means and DTC clustering (as shown in the figure below), the two models exhibit similar performance across different numbers of clusters. This suggests that while DTC offers specific advantages in capturing temporal patterns, both methods achieve comparable forecasting accuracy in this context.

![Comparison of Average RMSE for KMeans and DTC Clustering](images/rmse_comparison.png)
![Cluster Visualization](images/cluster_visualization.png)

---
## Requirements
- Python 3.x
- Libraries: `tensorflow`, `scikit-learn`, `pandas`, `numpy`, `matplotlib`
