README FILE

TEAM 4
AIT 614-001

INTRODUCTION:
This project focuses on developing a risk-based prioritization model for bridge maintenance using historical bridge condition data from the FHWA InfoBridge platform. By leveraging big data analytics and machine learning techniques, the project aims to assist policymakers and transportation authorities in making informed decisions to improve public safety and optimize resource allocation for bridge maintenance.

PROBLEM STATEMENT:
Aging and deteriorating bridge infrastructures in the United States pose significant challenges, compounded by funding constraints. This project addresses the need for a systematic approach to prioritize bridge maintenance by analyzing historical data to identify high-risk bridges and suggest efficient maintenance strategies.

OBJECTIVE:
- Collect and clean historical bridge data from the FHWA InfoBridge platform.
- Perform exploratory data analysis (EDA) to identify critical patterns and trends.
- Develop machine learning models to predict bridge deterioration and risk levels.
- Integrate environmental, structural, and traffic exposure factors into the analysis.
- Provide actionable insights to prioritize maintenance efforts.

SOLUTION WORKFLOW:
1. Data Preparation
- Data Source: FHWA InfoBridge platform.
- Data Cleaning:
  a. Address missing values, inconsistencies, and duplicates.
  b. Standardize column names and feature formats.
  c. Handle outliers in environmental and structural data.
-GIS Integration (ArcGIS Application):
  a. Imported bridge coordinate data (latitude/longitude) from the FHWA dataset into ArcGIS.
  b. Ensured all spatial layers used a consistent Coordinate Reference System (CRS).
  c. Integrated external geospatial datasets, including floodplain maps, seismic hazard zones, and traffic density layers.
  d. Performed spatial joins to enrich each bridge record with environmental risk attributes.
  e. Applied buffer analysis to assess the impact of surrounding infrastructure and environmental hazards.
  f. Exported the enriched geospatial dataset for further EDA and machine learning analysis.

2. Exploratory Data Analysis (EDA)
- Analyze bridge condition ratings, traffic exposure, and environmental factors.
- Generate visualizations (e.g., histograms, scatter plots, bar charts) to uncover trends and correlations.
- Summarize insights for feature selection and model development.

3. Feature Selection
- Methods:
  a. Chi-Squared Test for categorical variables.
  b. Logistic Regression for numerical variables.
  c. Random Forest for feature importance scoring.
- Final Features: Selected features with significant predictive power for bridge conditions.

4. Data Modeling
- Models Used:
  a. Random Forest Classifier: Predict high-risk and low-risk bridges.
  b. Gradient Boosted Trees (GBT): Assess environmental factors  impact.
  c. Linear Regression: Analyze categorical factors influencing deterioration.
- Machine Learning Pipeline:
  a. Feature engineering and transformation.
  b. Model training and evaluation using cross-validation.
  c. Metrics: Accuracy, ROC-AUC, F1-score.

5. Results
- Key Insights:
  a. Structural ratings (deck, superstructure, substructure) are the most significant risk determinants.
  b. Environmental factors vary in importance based on regional climates.
  c. Specific materials and designs significantly influence bridge durability.
- Model Performance:
  a. Random Forest Classifier achieved 99% accuracy.
  b. GBT demonstrated strong performance for environmental features with an ROC-AUC of 0.7417.


EXAMPLES:
Input:
- Structural Condition Ratings: Deck = 5, Superstructure = 4, Substructure = 3.
- Environmental Data: Min Temp = -5 C, Max Temp = 35 C, Humidity = 70%.

Output:
- Risk Prediction: High Risk.
- Recommended Action: Immediate maintenance for substructure.
- Contribution Analysis: Deck condition (47.8%), Superstructure (37.2%), Environmental Factors (15%).

SETUP INSTRUCTIONS:

Environment Setup
1. Install the required Python libraries:
   pip install pyspark databricks sklearn matplotlib numpy pandas

2. Configure Databricks for distributed data processing.
3. Load the dataset from the path - spark.read.format("csv").option("header", "true").option("inferSchema", "true").load("dbfs:/FileStore/shared_uploads/sshah62@gmu.edu/Team_4.csv. 
   change the path as per the user's system.

Dataset Details:
- Source: FHWA InfoBridge (https://infobridge.fhwa.dot.gov/Data).
- Features: Structural ratings, traffic exposure, environmental factors.
- Dataset file named as Team 4.csv

Additional Notes:
- Ensure compatibility with PySpark and Databricks for large-scale data processing.
- Use cross-validation techniques to validate model reliability.
- Visualizations are generated using Matplotlib and integrated within Databricks notebooks.
