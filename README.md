# GB-Electricity_and_Emission_Prediction

## Description 
This project develops a linear regression model to predict future values in GB electricity generation and carbon intensity for 2024-2025. In the visualisation section, changes in coal and wind energy are highlighted as key drivers of more sustainable electricity generation. As a result, the forecasting and analysis will assist SMEs and electricity suppliers in strategically adjusting their trajectories for electricity consumption and development.

> [!NOTE]
> *The original LSTM model was replaced due to its limitations with single-variable inputs, and that compromised its effectiveness. In its place, a multivariate linear regression model was chosen for its ability to handle multiple variables simultaneously. This new model not only reduces complexity but also improves effectiveness and enhances readability, to better meet the project's illustrative needs here.*

## Analytics Background
Leveraging machine learning for electricity and carbon intensity prediction offers **three key advantages** for relevant entities:

1. **Simplicity and interpretability**
   - Use linear regression to create a straightforward model that is easy to interpret for predicting electricity generation and carbon intensity.
   - Identify key factors influencing outcomes, this help SMEs and electricity suppliers understand trends and relationships.

2. **Informed strategic planning**
   - Leverage linear regression to forecast future electricity generation and carbon intensity accurately.
   - Support data-driven decisions for operational planning, cost management, and sustainability initiatives.

3. **Scalability and adaptability**
   - Apply scalable linear regression models that can be quickly adjusted with new data.
   - Enable SMEs and electricity suppliers to adapt to changing market conditions and enhance decision-making over time.

## Data Input and Preparation

### 1. Feature names
| DATETIME   | GAS  | COAL | NUCLEAR | WIND | HYDRO | IMPORTS | BIOMASS | OTHER | SOLAR | STORAGE | GENERATION | CARBON_INTENSITY | LOW_CARBON | ZERO_CARBON | RENEWABLE | FOSSIL | GAS_perc | COAL_perc | NUCLEAR_perc | WIND_perc | HYDRO_perc | IMPORTS_perc | BIOMASS_perc | OTHER_perc | SOLAR_perc | STORAGE_perc | GENERATION_perc | LOW_CARBON_perc | ZERO_CARBON_perc | RENEWABLE_perc | FOSSIL_perc |
|------------|------|------|---------|------|-------|---------|---------|-------|-------|---------|------------|------------------|------------|-------------|-----------|--------|----------|-----------|--------------|-----------|------------|--------------|-------------|------------|------------|--------------|----------------|-----------------|----------------|---------------|--------------|

### 2. Data cleansing  
Key steps for preparing data for modeling from the 31 features:

- **Calculate sums:** Aggregate weekly, monthly, seasonal, and annual totals for each energy source and carbon intensity.
- **Set decimal precision:** Round data values to two decimal places for clarity.
- **Convert units:**
  - Change total energy generation from **kWh to GW**
  - Change carbon intensity from **gCO2/kWh to kgCO2/kWh** for better readability.
- **Recalculate source percentages:** When summing data, calculate each source's percentage by dividing its generation by the total, rather than summing individual percentages, to accurately reflect contributions.

#### Note: You can find the dataset and feature explanations stored in the 'Data_sources' folder.

## Visualisation

### 1. Renewables vs. Carbon intensity
![image](https://github.com/user-attachments/assets/232796e3-7a3f-4f87-89fa-25c55aeceddb)

As shown, the carbon intensity, represented by the red line, slightly increased from 7.79k in 2009 to a peak of 8.86k in 2012, before continuously reducing to 2.61k in 2023. In contrast, renewable generation started at 15.43k in 2009 and gradually climbed to 191.10k in 2023. This chart clearly demonstrates that renewables have driven the dramatic decrease in carbon intensity over the observed period.

### 2. Quarterly trends of Wind and Solar
![image](https://github.com/user-attachments/assets/a9ebb1e6-084b-4676-965a-9faeeaf4b35f)

The chart reveals distinct seasonal patterns in renewable energy generation, with the second and third quarters marked in grey. Wind energy dominates in the first and fourth quarters, while solar energy sees its peak in the shaded mid-year months. Despite stable solar production between 2017 and 2022, the graph underscores a remarkable surge in wind energy within the GB electricity sector, soaring 21-fold from early 2009 to the end of 2023.

### 3. Energy Evolution
![image](https://github.com/user-attachments/assets/f9f0824c-26ad-4574-9c71-e67a9d5b10d5)

Between 2009 and 2023, the most striking shift is the transition from fossil fuels to renewable energy. Fossil fuel generation plummeted by 39%, driven largely by the near-elimination of coal, while renewables surged by 44%, with wind energy alone increasing by 32%. Although nuclear energy is emissions-free, it is not viewed as fully sustainable as renewables and has seen a 4% decline.

> [!TIP]
> Since GitHub does not support interactive visualisations, click **'Open In Colab'** at the top of the *Electricity_Prediction.ipynb* file to view all visualisations in the Colab notebook.

## Forecasting Modelling

Ridge and Lasso linear regression models, combined with grid search, are used for this forecasting task. The models split the data into a training set (2009-2021) and a test set (2021-2023) to predict values for 2024-2025. After optimising the alpha parameter, the Lasso model proved better in prediction based on cross-validated Mean MSE, MAE, and R². The forecast for gas energy, shown below, is derived using the Lasso regression model. The Lasso regression drives irrelevant coefficients to zero, effectively capturing underlying patterns while excluding outliers.
![image](https://github.com/user-attachments/assets/a3078a06-45b2-4f4f-945d-e1d7da2b86db)

## Conclusion
- **Carbon intensity:** Based on historical data and forecast trends, carbon intensity is expected to remain stable for the next few years before declining rapidly. The continuous development of renewables makes achieving zero-carbon electricity between 2030 and 2035 plausible, although completely eliminating fossil energy in GB electricity generation will be challenging.
- **Overall Generation:** The near-elimination of coal has created space for the expansion of wind energy. Meanwhile, other renewable sources like solar, hydro, and biomass have shown steady growth, promising to replace gas and nuclear as leading contributors. Great Britain's electricity supply is striding toward a zero-carbon future, and following this trend, the UK's net-zero goal for 2050 is absolutely achievable!
- **Recommendation:** With increasing regulatory and societal focus on sustainable transition, it is advisable to prepare for phasing out fossil energy and gradually replacing it with low-carbon alternatives.
   - **For SMEs:** Switching to a greener electricity tariff with lower emissions can lead to cost savings, improved efficiency, regulatory compliance, and enhanced reputation.
   - **For Electricity Suppliers:** It is essential to actively reduce fossil fuel supply and ensure a smooth transition to zero-carbon energy. This can be achieved by effectively leveraging the periodic availability of renewables and energy storage solutions.
 
## Contents

**Table of Contents**

1. **Data Import and Preparation**
   - 1.1 Import Library and Read the File
   - 1.2 Basic Data Quality Check
   - 1.3 Data Processing
3. **Data Visualisation**
   - 2.1 Energy Trends
   - 2.2 Evolution of Energy Proportions
   - 2.3 Weight Analysis
   - 2.4 Correlation Validation
   - 2.5 Carbon Intensity Trends
3. **Time-Series Prediction**
   - 3.1 Linear regression Prediction
      - 3.1.1 Ridge Regression
      - 3.1.2 Lasso Regression
      - 3.1.3 Model Optimisation
   - 3.2 Prediction Data Processing
   - 3.3 Prediction Visualisation
  
---

| Project                                                                                                                                          | Author    |
|--------------------------------------------------------------------------------------------------------------------------------------------------|-----------|
| [GB Electricity and Emission Prediction](https://github.com/Yuxi-Cn/GB-Electricity_and_Emission_Prediction/blob/main/Electricity_Prediction.ipynb) | Yuxi Chen |
