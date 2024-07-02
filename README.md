# Google-Cloud-Storage-to-Bigquery-to-Lookup-Studio

# Air Temperature Analysis Project

## Project Overview
This project involves analyzing air temperature data using Google Cloud Platform (GCP) services. The dataset is sourced from NOAA and stored in Google Cloud Storage, processed with BigQuery, and visualized through Google Data Studio.

### Public Dashboard
You can view the interactive dashboard [here](https://lookerstudio.google.com/reporting/4c21dfa2-7c42-4246-9d00-0dda3fd43cb1).

![Dashboard Preview](https://github.com/lbryant-sss/Google-Cloud-Storage-to-Bigquery-to-Lookup-Studio/blob/main/looker%20dashboard%20report%202.PNG
)

## Project Architecture
![Project Flow Chart](https://github.com/lbryant-sss/Google-Cloud-Storage-to-Bigquery-to-Lookup-Studio/blob/main/project%20architecture.png
)
### Data Source
- **Dataset**: NOAA Global Surface Summary of Day (GSOD)
- **Date Range**: January 1, 1998, to January 2, 2024
- **Parameters**: Air temperature, among other meteorological data

### Google Cloud Platform Components
1. **Google Cloud Storage**
   - **Purpose**: Store CSV files of the dataset
   - **Bucket Name**: `global-marine-weather-data`
   ![Cloud Storage Bucket](https://github.com/lbryant-sss/Google-Cloud-Storage-to-Bigquery-to-Lookup-Studio/blob/main/bucket.PNG)  
   
2. **BigQuery**
   - **Purpose**: Query and process the data
   - **Dataset**: `global_marine_weather_data_dataset`
   - **Table**: `global_marine_weather_data_dataset_table`
   - ![Bigquery Table](https://github.com/lbryant-sss/Google-Cloud-Storage-to-Bigquery-to-Lookup-Studio/blob/main/table.PNG)
   
### Data Processing Workflow
1. **Data Upload**
   - Upload CSV files to Google Cloud Storage.

2. **Data Ingestion**
   - Load CSV files from Cloud Storage into BigQuery.
   - Define the schema to match the structure of the dataset.

3. **Data Querying**
   - Perform SQL queries in BigQuery to analyze air temperature data.
   - Example Query:
     ```sql
     SELECT
       DATE,
       AVG(temperature) as avg_temperature
     FROM
       `your_project.your_dataset.your_table`
     GROUP BY
       DATE
     ```
   ![Example Query](https://github.com/lbryant-sss/Google-Cloud-Storage-to-Bigquery-to-Lookup-Studio/blob/main/bigquery.PNG)
### Data Visualization
1. **Google Data Studio**
   - **Connection**: BigQuery
   - **Report**: Air Temperature Analysis
   - **Visualizations**: Line charts, bar charts, tables, and maps.

### Report
- **Link**: [Google Data Studio Report](https://lookerstudio.google.com/reporting/4c21dfa2-7c42-4246-9d00-0dda3fd43cb1)

## How to Use
1. **View the Dashboard**: Access the public link to explore the interactive visualizations.
2. **Data Exploration**: Use the filters and date range selectors to interact with the data.
3. **Insights**: Analyze the trends and patterns in air temperatures over the specified period.

## Future Work
- **Additional Metrics**: Incorporate more weather parameters like precipitation and wind speed.
- **Predictive Analysis**: Use BigQuery ML for forecasting future temperatures.
- **Enhanced Visualizations**: Add more interactive elements and detailed charts.

## Conclusion
This project demonstrates the integration of GCP services to analyze and visualize large datasets. The interactive dashboard provides valuable insights into air temperature trends over time.

## License
This project is licensed under the MIT License.

