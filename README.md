# GB-Electricity_and_Emission_Prediction

## Description 
This project develops a linear regression model to predict future values in GB electricity generation and carbon intensity for 2024-2025. In the visualisation section, changes in coal and wind energy are highlighted as key drivers of more sustainable electricity generation. The forecasting results will assist SMEs and electricity suppliers in strategically adjusting their trajectories for electricity consumption and development.

*Note: The original LSTM model was replaced due to its limitations with single-variable inputs, and that compromised its effectiveness. In its place, a multivariate linear regression model was chosen for its ability to handle multiple variables simultaneously. This new model not only reduces complexity but also improves effectiveness and enhances readability, to better meet the project's illustrative needs.*

## Analytics Background
Leveraging machine learning for electricity and carbon intensity prediction offers **three key advantages** for relevant entities:

1. **Simplicity and Interpretability**
   - Use linear regression to create a straightforward model that is easy to interpret for predicting electricity generation and carbon intensity.
   - Identify key factors influencing outcomes, this help SMEs and electricity suppliers understand trends and relationships.

2. **Informed Strategic Planning**
   - Leverage linear regression to forecast future electricity generation and carbon intensity accurately.
   - Support data-driven decisions for operational planning, cost management, and sustainability initiatives.

3. **Scalability and Adaptability**
   - Apply scalable linear regression models that can be quickly adjusted with new data.
   - Enable SMEs and electricity suppliers to adapt to changing market conditions and enhance decision-making over time.

## Data Input and Preparation

### Feature names
| DATETIME   | GAS  | COAL | NUCLEAR | WIND | HYDRO | IMPORTS | BIOMASS | OTHER | SOLAR | STORAGE | GENERATION | CARBON_INTENSITY | LOW_CARBON | ZERO_CARBON | RENEWABLE | FOSSIL | GAS_perc | COAL_perc | NUCLEAR_perc | WIND_perc | HYDRO_perc | IMPORTS_perc | BIOMASS_perc | OTHER_perc | SOLAR_perc | STORAGE_perc | GENERATION_perc | LOW_CARBON_perc | ZERO_CARBON_perc | RENEWABLE_perc | FOSSIL_perc |
|------------|------|------|---------|------|-------|---------|---------|-------|-------|---------|------------|------------------|------------|-------------|-----------|--------|----------|-----------|--------------|-----------|------------|--------------|-------------|------------|------------|--------------|----------------|-----------------|----------------|---------------|--------------|

### Data Cleansing  
Key steps for preparing data for modeling from the 31 features:

- **Calculate Sums:** Aggregate weekly, monthly, seasonal, and annual totals for each energy source and carbon intensity.
- **Set Decimal Precision:** Round data values to two decimal places for clarity.
- **Convert Units:**
  - Change total energy generation from **kWh to GW**
  - Change carbon intensity from **gCO2/kWh to kgCO2/kWh** for better readability.
- **Recalculate Source Percentages:** When summing data, calculate each source's percentage by dividing its generation by the total, rather than summing individual percentages, to accurately reflect contributions.

#### Note: You can find the dataset and feature explanations stored in the 'Data_sources' folder.

## Visualisation


## Forecasting Modelling

## Result and Conclusion
