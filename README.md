# 1158238
comp647, James Yeon, 1158238

# create repository - 14/07/2025
1158238

# Upload dataset - 29/07/2025
crop_yield.csv, crop_yield_dataset.csv

# create folder notebooks
crop_yield_datapreprocessing.ipynb

# Weather Data Extraction – Steps
1. Load the crop_yield_dataset.csv file
    Load the raw dataset containing crop, soil, weather, and yield information.
2. Inspect the data
    Check the structure, column names, and data types using df.info() and df.head().
3. Extract weather-related columns
    Select only the relevant weather features such as Date, Temperature, Humidity, and Wind_Speed.
4. Split the Date column
    Convert the Date column to datetime format and extract Year, Month, and Day into separate columns.
5. Save the weather dataset
    Export the cleaned and structured weather data into a new CSV file (e.g., crop_weather_data.csv).