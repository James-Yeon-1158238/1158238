# 1158238
comp647, James Yeon, 1158238

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


# Review after the first analysis - 18/08/2025
During the first round of analysis, I treated Crop_Yield values of 0 as missing and replaced them with the mean/median. However, while conducting the EDA, I realized that a Crop_Yield value of 0 actually carries meaningful information, so I restarted the work from the beginning.


# Data preprocessing rework in progress - 27/08/2025
- Split the files into Weather and Soil Type without modifying Crop_Yield
- create files: crop_soiltype_data_0.csv, crop_weather_data_0.csv

# EDA Weather - 30/08/2025
 - task_03_crop_yield_weather_Crop_Yield_0.ipynb 

# EDA Soil_Quality - 30/08/2025
 - task_03_crop_yield_soiltype_median.ipynb 


 # Weather + SoilType Integrated Analysis Preparation - 2025/09/06
- Re-merge Weather and Soil Type data into a single file  

# Data preprocessing rework in progress - 06/09/2025
- Split the files into Weather and Soil Type without modifying Crop_Yield
- create files: ccrop_yield_cleansing_data.csv

# EDA - 04/09/2025
 - Conduct correlation and impact analysis of Crop_Yield based on the integrated dataset  
 - task_04_crop_yield_EDA.ipynb

 # Exploratory Data Analysis Completed - 06/09-2025