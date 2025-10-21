# Traffic & Air Quality Visualization Dashboard

## Aim
This project is intended to **exhibit the interplay between traffic congestion and air pollution** in several urban areas. The workflow transforms unprocessed traffic and air quality datasets into daily and hourly trend charts, static, and interactive visualizations that make it easier to comprehend the relationships and interactions among traffic volume, PM2.5, NO₂, and AQI.

The major goals are:  
- Merging and aggregating datasets of traffic and air quality  
- Calculating daily and hourly trends  
- Illustrating the relationship between traffic and pollutants  
- Mapping pollution levels geographically  
- Delivering static outputs (PNG) for the purpose of the portfolio or reports  

---

## Dataset Description
For the purpose of the project, two CSV files have been used:  

1. **Traffic data (`raw/traffic.csv`)**  
   - `timestamp`: Datetime of measurement  
   - `city`: City name  
   - `traffic_volume`: Number of vehicles  

2. **Air quality data (`raw/air_quality.csv`)**  
   - `timestamp`: Datetime of measurement  
   - `city`: City name  
   - `pm25`: PM2.5 concentration  
   - `no2`: NO₂ concentration  
   - `aqi`: Air Quality Index  
   - `temperature`: Ambient temperature  
   - `wind_speed`: Wind speed  

To ensure consistency in the data, all the measurements have been **hourly resampled** and then merged city-wise.

---

## Pipeline Overview
The script `visualization_no_kaleido.ipynb` carries out the following stages:

1. **Data Loading & Cleaning**  
   - Reads in traffic and air quality data  
   - Aligns numeric columns to hourly by resampling  
   - Joins cities and timestamps to merge datasets  

2. **Add City Coordinates**  
   - Maps latitudes and longitudes to cities for mapping purposes  

3. **Exploratory Data Analysis (EDA)**  
   - Descriptive statistics are computed  
   - Daily trends for traffic are aggregated and Seaborn  
   - Geospatial map with Folium, showing PM2.5 and traffic intensity  

4. **Visualizations**  
   - **Visual 1:** Dual-axis time series (traffic vs AQI) using Matplotlib  
   - **Visual 2:** Weekly heatmap of PM2.5 using Seaborn  
   - **Visual 3:** Scatter plot with regression (Traffic vs PM2.5) using Seaborn  
   - **Visual 4:** Geospatial map with Folium, showing PM2.5 and traffic intensity  

5. **Export Outputs**  
   - Saves visualizations as PNG files in `images/`  
   - Saves interactive Folium map as `HTML`  

---

## How to Use the Script
1. Place your datasets in the `raw/` folder:  
   - `raw/traffic.csv`  
   - `raw/air_quality.csv`  

2. Open and run the Jupyter notebook:  

```bash
jupyter notebook notebooks/visualization_no_kaleido.ipynb