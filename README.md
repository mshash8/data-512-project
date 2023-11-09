# data-512-project

# Project Goal
The goal of the project is to analyze wildfire impacts on a specific city in the US. This analysis has the potential to provide valuable insights for policy makers, city managers, city councils, and other civic institutions, enabling them to develop informed plans on how to address or whether to consider plans for mitigating future wildfire impacts.

# Data Acquistion and API Documentation

## Data Acquistion
The section below details the steps for data acquistion. We have:

1. A geojson [file](https://drive.google.com/file/d/1khouDmMaZyKo0y5WkFj4lu7g8o35x_98/view?usp=drive_link) dataset collected and aggregated by the US Geological Survey. This contains fire polygons for wildfires that have occurred across the USA. 
2. An API [file]([https://www.census.gov/data/tables/time-series/demo/popest/2020s-state-total.html](https://aqs.epa.gov/aqsweb/documents/data_api.html)) to obtain the Air Quality Estimates for regions in the USA.
3. A [spreadsheet](https://docs.google.com/spreadsheets/d/1cmTW5fgU3KyH6JbrRao-qWjzu2GovKk_BkA7a-poGFw/edit?usp=drive_link) listing the assignments of different cities.

# Platform
This project was run on jupyter notebook on localhost. 

# Steps to Reproduce these Results
Data Acquistion, Data Preparation, and Data Analysis are key phases within this project:

* Step 1: Getting the Wildfire and AQI data
  - Data is obtained from the data sources listed above and to make API calls to get further information required for analysis.
* Step 2: Filtering out the Data for the Scope of this Sssignment
  - The data from the previous step is filtered to include only wildfires in a 1250 radius from the source city and for the years 1963-2023.
* Step 4: Creating a Smoke Estimate
  - Once the filtered data is obtained, the smoke estimate is calculated using attributes in the wildfire data.
* Step 5: Time Series Forecasting and Prediction
  - With the smoke estimate for each year available, a time series forecasting technique is utilized to predict the smoke for future dates for the city of interest.
* Step 5: Visualization and Analysis
  - Visualizations and Analysis is done based on prompts provided by the instructor:
      1. Produce a histogram showing the number of fires occurring every 50 mile distance from your assigned city up to the max specified distance.
      2. Produce a time series graph of total acres burned per year for the fires occurring in the specified distance from your city.
      3. Produce a time series graph containing your fire smoke estimate for your city and the AQI estimate for your city.

# Documentation
This project adheres to recommended best practices for replication and documentation:

Jupyter Notebook: detailed comments for data acquistion, processing, and analysis.

README File: Offers a general overview of the project, outlining its objectives, data sources, data processing procedures, and standards for reproducibility.

LICENSE File: Contains the MIT LICENSE for the project's code, ensuring it is freely usable and the [Creative Commons License](https://creativecommons.org/licenses/by/4.0/). 

# Special Considerations
* The GeoJSON dataset from USGS is extensive, containing approximately 136,000 fire occurrences that require thorough analysis. Although loading this data was made more straightforward with the Reader written by Prof. David McDonald, filtering the data required parsing through these rows to include only those fire occurrences falling within the scope of this assignment, which consumed a significant amount of time.

* Extensive error handling was also necessary, as not all fields were present in every data row. For instance, the 'rings' parameter needed to be verified and handled accordingly.

* It is also important to note that data is available for all years except for 2021, 2022, and 2023 for the analysis.

* The AQI data presents its own set of challenges. For instance, in the city of study, Lewiston, Idaho, there are no stations within the city or within a 25-mile radius of it. The closest station is located 50 miles from the city. Additionally, there is no data available for all the years in a single station. Data from multiple station responses must be appended.

* Due to variations in the years of operation for different weather stations, data consolidation is necessary across two distinct stations.

* Furthermore, the response from the EPA API does not always contain the 'aqi' parameter, requiring exception handling. In my city locations, there was also an absence of data for gaseous pollutants, with only particulate pollutants available. This specific scenario also calls for separate handling.

# License
This project is open-source and follows the MIT License. You are free to use and modify the code according to the terms of the MIT License. 

# Data Files 

1. **Path:** data/predictions.json - This file contains the predictions of smoke in Lewiston, Idaho for the years 2024-2049.

year (int) : predicted_smoke_estimate (int)

2. **Path:** data/aqi.json - This file contains the AQI estimates near Lewiston, Idaho for the years 1986-2023.

year (int) : aqi_estimate (int)


# Research Implications
As part of this project, I had the opportunity to explore wildfires in the USA and its impact on air quality.






