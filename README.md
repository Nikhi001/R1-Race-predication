# R1-Race-predication

## Overview
This study focuses on predicting F1 race outcomes using various machine learning models. We begin by merging multiple data files, conducting data cleaning, feature selection, data transformation, exploratory data analysis (EDA), and applying six machine learning models for classification. The target variable is the race outcome (win or no win), based on driver performance and race characteristics.

## Step 1: Importing Libraries
We start by importing essential Python libraries:

Pandas for data manipulation and merging.
Matplotlib and Seaborn for data visualization during EDA.
Sklearn for machine learning model implementation.

## Step 2: Merging Data Files
We merged 14 datasets containing F1 race data. These files were combined based on common columns such as Driver, Date, or Grand Prix. After merging, the dataset contained the following 22 key columns:

DriverCars: Car used by the driver.  
Date: Date of the race.  
Driver: Name of the driver.  
Grand Prix: Race event name.    
StandingPoints: Points in the overall standings.  
Raceposition: Final position in the race.  
Year: Year of the race.  
StandingPosition: Driver's overall position in the standings.  
Winner: Name of the race winner.  
Winnerlaps: Number of laps completed by the winner.  
FinishTime: Time taken by the winner to finish the race.  
Winnerposition: Final position of the race winner.  
No: Driver number.  
PTS: Points earned by the driver in the race.  
WinnerCars: Car used by the winner.  
QulifyPositions, QualifyLaps, Q1, Q2, Q3, and Time: Qualifying session details.  

## Step 3: Data Cleaning
Several columns were deemed irrelevant or redundant and were removed:

Columns such as Unnamed: 0, DriverPoints, winnerlaps, FinishTime, WinnerPosition, QulifyPositoins, QualifyLaps, Time, DriverCars, and WinnerCars were dropped.
Additionally, missing values were handled through imputation or removal, and outliers were detected and addressed using techniques like Interquartile Range (IQR).

## Step 4: Exploratory Data Analysis (EDA)
EDA was conducted to uncover trends, correlations, and patterns in the data:

**Correlation Analysis:** A heatmap was used to visualize relationships between variables like PTS, Raceposition, and StandingPoints.  
**Driver Performance Trends:** Trends in driver performance across different races and seasons were examined using line graphs.  
**Qualifying Positions vs. Race Outcome:** The relationship between a driver’s qualifying position and final race position was explored.
Visualization tools like histograms and box plots were used to analyze distributions and detect outliers in the data.

## Step 5: Feature Selection
The following 22 key features were selected for further analysis, and some new features were engineered to capture additional insights:

**Engineered Feature** - RaceWin: Created a binary column indicating if a driver won the race (1 for win, 0 otherwise).  
**Points Per Race:** A feature capturing the points earned by each driver per race.  

## Step 6: Data Transformation
Several transformations were applied to prepare the dataset for machine learning:

**Handling Categorical Data:** Categorical columns like Driver, Grand Prix, DriverCars, and WinnerCars were transformed using One-Hot Encoding.  

**Normalization and Scaling:** Numerical features like PTS, StandingPoints, Q1, Q2, Q3, and FinishTime were scaled using Standardization or Min-Max Scaling to ensure that all features contribute equally to the model.

**Date and Time Features:** Year and month were extracted from the Date column to capture temporal trends.

## Step 7: Final Dataset Preparation
After transformation, the dataset included the following types of features:

**Categorical Features:** Encoded versions of Driver, Grand Prix, DriverCars, and WinnerCars.  
**Numerical Features:** Scaled versions of PTS, StandingPoints, Q1, Q2, Q3, and FinishTime.  
**Engineered Features:** New columns like RaceWin, PointsPerRace, Year, and Month.  
The final dataset was split into training and testing sets (80% for training and 20% for testing).

## Step 8: Machine Learning Models
Six classification models were used to predict the race outcome (win or no win). The target variable was RaceWin.

**1. Logistic Regression**  
A simple, interpretable model for binary classification. It performed well with reasonable accuracy.

**2. K-Nearest Neighbors (KNN)**  
KNN used the proximity of data points to classify race outcomes. It provided moderate performance, especially in highly structured datasets.

**3. Support Vector Machine (SVM)**  
SVM performed robustly, especially in separating classes using a linear decision boundary. It was particularly useful for complex, non-linearly separable data.

**4. Naive Bayes**  
This model provided a fast and simple approach to classification by assuming feature independence. It was effective for large datasets but showed limited accuracy due to its simplistic assumptions.

**5. Decision Tree**  
Decision Tree models split the data based on important features and produced interpretable results. This model performed well but was prone to overfitting on complex datasets.

**6. Random Forest**  
Random Forest, an ensemble model, provided the best accuracy by averaging the predictions of multiple decision trees. It handled outliers and overfitting issues effectively.

Each model was evaluated using accuracy, precision, recall, and F1-score metrics, providing a comprehensive understanding of its performance.

## Step 9: Results and Conclusion
**Model Comparison:** Random Forest outperformed other models in terms of accuracy, followed by SVM and Decision Tree. Naive Bayes and KNN showed lower performance due to limitations in handling complex data structures.  

**Final Recommendations:** Based on the analysis, Random Forest is recommended for race outcome prediction due to its high accuracy and robustness.  

**Next Steps:** Further fine-tuning of model hyperparameters and exploring additional features (such as pit stop strategies or tire types) could improve performance even more.  
