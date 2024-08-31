# GB-Electricity_and_Emission_Prediction

## Description 
This project develops a linear regression model to predict future values in GB electricity generation and carbon intensity for 2024-2025. In the visualisation section, changes in coal and wind energy are highlighted as key drivers of more sustainable electricity generation. The forecasting results will assist SMEs and electricity suppliers in strategically adjusting their trajectories for electricity consumption and development.

> [!NOTE]
> *The original LSTM model was replaced due to its limitations with single-variable inputs, and that compromised its effectiveness. In its place, a multivariate linear regression model was chosen for its ability to handle multiple variables simultaneously. This new model not only reduces complexity but also improves effectiveness and enhances readability, to better meet the project's illustrative needs.*

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

As shown, the carbon intensity, which is represented by the red line, have a slight increase from 7.79k in 2009 to 8.86k in 2012 at peak, and continuously reduce to 2.61k in 2023. In contrast, renewable generation starts at 15.43k in 2009, gradually climbs to 191.10k in 2023. From this chart solely, the renewable undeniably drives the dramatic decrease of carbon intensity in the observed period.

### 2. Quarterly trends of Wind and Solar
![image](https://github.com/user-attachments/assets/a9ebb1e6-084b-4676-965a-9faeeaf4b35f)

The chart above highlights the seasonal patterns of renewable energy generation, with the second and third quarters shaded in grey. Wind energy is more active in the first and fourth quarters, while solar energy peaks in the shaded second and third quarters. However, solar production remained stable between 2017 and 2022. In contrast, the graph shows significant growth in wind energy within the GB electricity sector, with a 21-fold increase from the first quarter of 2009 to the last quarter of 2023.

### 3. Energy Evolution
![image](https://github.com/user-attachments/assets/f9f0824c-26ad-4574-9c71-e67a9d5b10d5)

Between 2009 and 2023, the most striking shift is the transition from fossil fuels to renewable energy. Fossil fuel generation plummeted by 39%, driven largely by the near-elimination of coal, while renewables surged by 44%, with wind energy alone increasing by 32%. Notably, although nuclear energy is emissions-free, it is not considered as fully sustainable as renewables and has seen a 4% decline.

> [!TIP]
> Since GitHub does not support interactive visualizations, click **'Open In Colab'** at the top of the *Electricity_Prediction.ipynb* file to view all visualisations in the Colab notebook.

## Forecasting Modelling

Ridge and Lasso linear regression models, combined with grid search, are used for this forecasting task. The models split the data into a training set (2009-2021) and a test set (2021-2023) to predict values for 2024-2025. After optimizing the alpha parameter, the Lasso model proved better in prediction based on cross-validated Mean MSE, MAE, and R². The forecast for gas energy, shown below, is derived using the Lasso regression model, which drives irrelevant coefficients to zero, effectively capturing underlying patterns while excluding outliers.
![image](https://github.com/user-attachments/assets/a3078a06-45b2-4f4f-945d-e1d7da2b86db)

## Result and Conclusion

