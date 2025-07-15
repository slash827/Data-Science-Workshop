# Asteroid Diameter Prediction
A machine learning project that predicts asteroid diameters using orbital and physical characteristics data from NASA's Jet Propulsion Laboratory.
About
This project develops predictive models to estimate asteroid diameters based on various astronomical features such as orbital parameters, magnitude measurements, and physical properties. The dataset contains information about asteroids including their orbital velocities, eccentricity, albedo, and other characteristics that can be used to predict their size.
Key Features

Data Enrichment: Enhanced the original dataset by connecting to NASA's API to fill missing values and obtain updated asteroid information
Multiple ML Approaches: Implemented and compared various regression models including Linear Regression, Decision Trees, Random Forest, and AdaBoost
Data Preprocessing: Comprehensive handling of missing values using three different strategies:

Removing rows with null values
Predicting missing values using auxiliary models
Filling nulls with mean values


Feature Engineering: Applied correlation analysis and feature selection to identify the most relevant predictors
Model Explainability: Used SHAP (SHapley Additive exPlanations) to understand feature importance and model decisions
Outlier Detection: Statistical approach to identify and remove extreme values that could negatively impact model performance

Dataset
The asteroid data was sourced from the Jet Propulsion Laboratory of California Institute of Technology (NASA) and includes features such as:

Albedo: Measure of reflectivity or intrinsic brightness
Eccentricity: Orbital shape parameter
Absolute Magnitude: Visual brightness measurement
PHA (Potentially Hazardous Asteroid): Hazard classification
MOID (Minimum Orbit Intersection Distance): Collision risk indicator
Orbital parameters: Semi-major axis, perihelion distance, inclination, etc.

Results
The Random Forest model achieved the best performance with:

R² Score: 0.98 (when filling null values)
Low Error Rate: 49% of predictions had less than 5% error
Robust Performance: Only 10% of predictions had more than 15% error

Model Performance Comparison
ModelRemove Nulls (R²)Fill Nulls - Prediction (R²)Fill Nulls - Mean (R²)Linear Regression0.810.550.55Decision Tree0.930.950.95Random Forest0.960.980.98AdaBoost0.670.770.76
Key Insights
Through SHAP analysis, we discovered that the most important features for predicting asteroid diameter are:

Absolute Magnitude Parameter - Lower values indicate larger asteroids
Albedo - Lower reflectivity values correlate with larger diameters
Orbital Motion Parameters - Mean motion and orbital periods provide additional predictive power

Technical Implementation

Language: Python
Key Libraries:

pandas, numpy for data manipulation
scikit-learn for machine learning models
matplotlib, seaborn for visualization
SHAP for model explainability


Data Processing: Statistical outlier detection using Z-score (±3 standard deviations)
Feature Selection: Correlation-based filtering (features with |correlation| > 0.05 with target)
Validation: Train-test split with comprehensive evaluation metrics

Getting Started

Clone this repository
Install required dependencies: pip install -r requirements.txt
Open the Jupyter notebook: Asteroid_ds_workshop.ipynb
Run the cells to reproduce the analysis and results

Future Work

Hyperparameter tuning for optimal model performance
Implementation of validation set for more robust model evaluation
Extension to predict other asteroid characteristics
Integration of additional astronomical data sources


This project demonstrates the application of machine learning techniques to astronomical data, contributing to our understanding of asteroid characteristics and potentially supporting space mission planning and planetary defense initiatives.
