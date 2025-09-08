# 1158238
comp647, James Yeon, 1158238

# Project Purpose
The purpose of this project is to analyze the impact of weather and soil data on crop yields and identify optimal environmental conditions for maximum productivity. By identifying key patterns and correlations through exploratory data analysis (EDA) and applying machine learning techniques to build predictive models, the goal is to provide practical guidance applicable to real-world agricultural environments.

# Data Cleaning & EDA – Three Iterations Summary
## TL;DR
- Iteration 1: Treated Crop_Yield=0 as missing → Conducted separate analyses for Weather and SoilType → Identified interpretation issues
- Iteration 2: Kept Crop_Yield=0 as valid observations → Still analyzed Weather and SoilType separately → Found that zero yields are strongly linked to environmental conditions (e.g., temperature, pH)
- Iteration 3: Retained Crop_Yield=0 and merged Weather + SoilType into a single integrated dataset → Built a unified analysis pipeline → Enabled detection of interaction effects and better control of covariates

# Iteration 1 – Zero Values Treated as Missing, Separate EDA
## Timeline/Output: Initial EDA round (early notebook version)
## Cleaning Decision: Crop_Yield=0 → treated as missing values, imputed with mean/median
## Analysis Approach: Weather and SoilType data analyzed separately, focusing on correlations, distributions, and descriptive statistics
## Limitations / Lessons Learned
- Replacing zero yields with missing values led to loss of meaningful information (e.g., crop failure or unsuitable conditions)
- Patterns were visible within Weather and Soil datasets, but interaction effects (e.g., temperature × pH) could not be captured

**Conclusion: Design change needed to treat zero yields as valid observations**

# Iteration 2 – Zero Values Retained, Still Separate EDA
## Timeline/Output: Intermediate EDA round (Weather/Soil analyzed in separate notebooks)
## Cleaning Decision: Crop_Yield=0 retained as valid data (interpreted as failure cases)
## Analysis Approach: Weather and Soil datasets still analyzed separately
## Key Insights
- Frequency of zero yields increased under extreme temperatures (very low or very high)
- Yields were more stable within the pH 6.0–7.5 range; outside this range yields dropped significantly, with more zero yields observed
- N–P–K showed strong positive correlations, moving together as indicators of soil fertility
- Soil_Quality aligned with nutrient levels, with higher quality associated with higher yields
## Limitations / Lessons Learned
- Separate analyses of Weather and Soil were insufficient to control for covariates or to capture interaction effects

**Conclusion: Required merging into a single, integrated dataset for more comprehensive analysis**

# Iteration 3 – Zero Values Retained, Unified Dataset EDA
## Timeline/Output: Integration prepared on 2025-09-06
- Unified file: crop_yield_cleansing_data.csv
- Notebook: task_04_crop_yield_EDA.ipynb
## Cleaning/Preprocessing
- Kept Crop_Yield=0 as valid and meaningful labels of crop failure/unfavorable conditions
- Data type conversions (date → year/month/day), categorical standardization (Crop_Type, Soil_Type)
- Outlier review (IQR/Z-score), but avoided excessive removal before identifying causes
## Analysis Approach
- Single Weather + SoilType table analyzed for correlations, distributions, pivot tables, and conditional aggregations
- Threshold variables such as pH and temperature binned into ranges for yield comparison
- (Optional) PCA applied for multivariate structure → explored crop clusters under similar soil and weather environments
## Preliminary Insights
- Critical ranges (≈pH 6.0–7.5, optimal temperature bands) strongly associated with zero yields
- N–P–K group and Soil_Quality consistently indicated higher yield signals
- Unified analysis enabled detection of interaction effects (e.g., pH × temperature, nutrients × soil type)
## Technical Advantages
- A single, reproducible pipeline created from one integrated source
- Direct applicability to downstream modeling (classification: 0 vs >0 yields, regression: continuous yield prediction)


# Summary raw data
- Total number of rows: 36520
- Start date (Min): 2014-01-01 00:00:00
- End date (Max): 2023-12-31 00:00:00
- Crop_Type: Wheat, Corn, Rice, Barley, Soybean, Cotton, Sugarcane, Tomato, Potato, Sunflower



# Analysis Variables
## Target Variable (Prediction Goal)
1. Crop_Yield
- Unit: kg/ha (or depending on dataset definition)
- Description: Crop production/yield → the main variable to be predicted

## Input Features (Explanatory Variables)
2. Crop Information
- Crop_Type (Categorical: Wheat, Corn, Rice, Barley, Soybean, …)
3. Weather Variables
- Temperature (°C, numerical)
- Humidity (% relative humidity, numerical)
- Wind_Speed (m/s, numerical)
4. Soil Variables
- Soil_Type (Categorical: Clay, Sandy, Loamy, Peaty, etc.)
- Soil_pH (Continuous, range approx. 4.0 – 8.5)
- N (Nitrogen, numerical)
- P (Phosphorus, numerical)
- K (Potassium, numerical)
- Soil_Quality (Soil quality index, continuous or ordinal)

# create repository - 14/07/2025
1158238

# Upload dataset - 29/07/2025
crop_yield.csv, crop_yield_dataset.csv

# commit title
 - taks[no]_[ddmmyyyy]_[Filename or task name]
   e.g. task02_05082025_EDA_weather_data
 - commit file name
   e.g. README

# create folder notebooks
- dataset
- dataset/raw
- dataset/processed
- notebooks

# Iteration 1 – Zero Values Treated as Missing, Separate EDA
# Weather and SoilType Data Extraction – Steps
1. Load the crop_yield_dataset.csv file
    Load the raw dataset containing crop, soil, weather, and yield information.
2. Inspect the data
    Check the structure, column names, and data types using df.info() and df.head().
3. Extract weather/SoilType-related columns
    Select only the relevant weather features such as Date, Temperature, Humidity, and Wind_Speed.
4. Split the Date column
    Convert the Date column to datetime format and extract Year, Month, and Day into separate columns.
5. Save the weather, Soil dataset
    Export the cleaned and structured weather and Soil data into a new CSV file (e.g., crop_weather_data.csv).

# EDA Weather 05/08/2025
 - task_02_crop_yield_weather_Crop_Yield_median.ipynb 

# EDA Soil_Quality 09/08/2025
 - task_02_crop_yield_soiltype_Crop_Yield_median.ipynb 

# Iteration 2 – Zero Values Retained, Still Separate EDA
# Review after the first analysis - 18/08/2025
During the first round of analysis, I treated Crop_Yield values of 0 as missing and replaced them with the mean/median. However, while conducting the EDA, I realized that a Crop_Yield value of 0 actually carries meaningful information, so I restarted the work from the beginning.

# Data preprocessing rework in progress - 27/08/2025
- Split the files into Weather and Soil Type without modifying Crop_Yield
- create files: crop_soiltype_data_0.csv, crop_weather_data_0.csv

# EDA Weather - 30/08/2025
 - task_03_crop_yield_weather_Crop_Yield_0.ipynb 

# EDA Soil_Quality - 30/08/2025
 - task_03_crop_yield_soiltype_median.ipynb 

# Iteration 3 – Zero Values Retained, Unified Dataset EDA
# Weather + SoilType Integrated Analysis Preparation - 2025/09/06
- Re-merge Weather and Soil Type data into a single file  

# Data preprocessing rework in progress - 06/09/2025
- Split the files into Weather and Soil Type without modifying Crop_Yield
- create files: ccrop_yield_cleansing_data.csv

# EDA - 04/09/2025
 - Conduct correlation and impact analysis of Crop_Yield based on the integrated dataset  
 - task_04_crop_yield_EDA.ipynb

 # Exploratory Data Analysis Completed - 08/09-2025