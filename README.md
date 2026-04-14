##Hadoop Big Data Processing: Wildfire Analysis

This project implements a big data pipeline to analyze wildfire occurrences in the United States using Apache Hadoop and Spark. It processes large-scale datasets to identify spatial and temporal trends in fire intensity (FRP) across California counties.

Project Tasks
Data Preparation: Cleanses raw CSV data, filters environmental attributes, and performs spatial joins to attribute wildfires to specific counties using US Census data.

Spatial Analysis: Computes total fire intensity per county within specific date ranges.

Temporal Analysis: Analyzes monthly fire intensity trends for specific counties and generates data for line charts and bar charts.

Fire Intensity Prediction: Uses Spark MLlib to build a regression model predicting fire intensity based on environmental factors like elevation, temperature, and fuel levels.

Visualization Support: Exports processed spatial data in Shapefile format for external mapping and CSV format for temporal charting.

Tech Stack
Language: Java

Frameworks: Apache Hadoop, Apache Spark, Beast (Spatial Data Framework)

Data Formats: CSV, Parquet, Shapefile

Build Tool: Maven

Installation
Clone the repository:

Bash
git clone https://github.com/JaimeVal24/Hadoop-Big-Data-Processing.git
Build the project:

Bash
mvn clean package
Usage
1. Data Preparation
Convert CSV to Parquet and attach county GEOIDs:

Bash
spark-submit --class <MainClass> target/Hadoop-Big-Data-Processing-1.0-SNAPSHOT.jar <input_csv> <county_data> <output_parquet>
2. Spatial Analysis
Generate county-level intensity data for a specific date range:

Bash
spark-submit --class <SpatialClass> target/Hadoop-Big-Data-Processing-1.0-SNAPSHOT.jar <input_parquet> <start_date> <end_date> <output_path>
Note: The resulting Shapefile can be imported into QGIS to generate choropleth maps.

3. Prediction Model
Train and test the fire intensity prediction model:

Bash
spark-submit --class <PredictionClass> target/Hadoop-Big-Data-Processing-1.0-SNAPSHOT.jar <input_parquet>
License
Distributed under the MIT License.
