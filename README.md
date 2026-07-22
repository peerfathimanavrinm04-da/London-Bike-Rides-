## **London Bike Rides** 
#### **Tool**: Python | Tableau
<br>
<img src = "https://github.com/peerfathimanavrinm04-da/London-Bike-Rides-/blob/daa0d67907bae73b10908e5a37228b87f4182bba/Screenshot%20(60).png">
<br>
### **Overview**
The London Bike Rides Dashboard analyzes over 3 million rides recorded between July 16, 2016 and October 10, 2016. It combines time-series trends, weather conditions, and environmental factors to uncover how external variables influence bike usage in London. By integrating ride counts with temperature, wind speed, and hourly distribution, the dashboard provides actionable insights into commuter behavior, peak usage times, and the impact of weather on cycling activity.

### PYTHON NOTEBOOK

#### 1. **Data Import & Initial Exploration**

- The dataset **london_merged.csv** was imported using **pandas** and contains **17,414 records** with 10 columns.
- Key features include:
    - **time** (timestamp of bike usage)
    - **count** (number of bikes rented per hour)
    - **weather conditions** (temperature, humidity, wind speed, weather codes)
    - **seasonal and holiday indicators**

Initial inspection (**shape , info() , value_counts()** ) confirmed data completeness and identified categorical variables such as **season** and **weather_code**.

#### 2. **Data Cleaning & Transformation**

- **Column Renaming:** Technical column names were replaced with descriptive, business-friendly labels **(e.g., cnt→countv , t1 → temp_real_C).**
- **Feature Engineering:**
    - Humidity values were converted into percentages for interpretability.
    - Dictionaries were created to map numeric codes to meaningful labels:
        - **Season: 0 → spring, 1 → summar, 2 → autumn, 3 → winter**
        - **Weather:** **1→ Clear, 2 → Scattered clouds, 3 → Broken clouds, 4→ Cloudy, 7 → Rain, 10 → Thunderstorm, 26 -. Snowfall.**
- **Data Type Adjustments:** Columns like **season** and **weather** were converted to string and mapped to descriptive text, improving readability for analysis and visualization.

#### 3. **Final Dataset Preparation**

- The transformed dataset now provides **human-readable insights**:
    - Example: Instead of weather _code = 3, the dataset shows **“Broken clouds”**.
    - Instead of season = 3, the dataset shows **“Winter”**.
- The cleaned dataset was exported to Excel **(london_rides_final.xlsx)** for reporting and dashboard integration.

### Summary of Dashboard Components

- **Total Rides**:
    - 3,081,816 rides during the study period.
- **Trend Analysis (Line Chart)**:
    - 10-day moving average of rides.
    - Highlights seasonal fluctuations and daily ride volumes.
    - Example: On **10-08-2016**, moving average rides = **36,936**.
- **Weather Breakdown**:
    - Clear skies: 22,250 rides
    - Scattered clouds: 14,956 rides
    - Broken clouds: 1,224 rides
    - Shows how weather conditions directly affect ride frequency.
- **Hourly Distribution (Bar Chart)**:
    - Peak hours: 7 AM, 3 PM, 7 PM, 11 PM (each ~4,500 rides).
    - Minimal activity between midnight and early morning.
    - Reveals commuter and leisure cycling patterns.
- **Temperature vs Wind Speed (Heatmap)**:
    - Cross-analysis of ride counts by temperature and wind speed.
    - Example:
        - At **19.9°C & 17.9 Kph wind**, rides peaked at **156,549**.
        - Cooler temps and higher winds reduced ride counts.
    - Demonstrates environmental sensitivity of cycling behavior.
