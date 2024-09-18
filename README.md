Data Preparation Project: FIFA 21 Player Dataset

## Project Overview
This project focuses on cleaning and preparing the FIFA 21 player dataset for analysis. The dataset contains information on player attributes such as age, nationality, club, and various performance metrics.
The primary goals of the data preparation process were to clean the data by handling missing values, removing irrelevant columns, standardizing data formats, and ensuring consistency across the dataset for further analysis and visualization.

## Source
The dataset was extracted from kaggle, the link will be included in this section
Main Attributes: Player name, nationality, age, club, physical attributes, performance metrics, and contract information.
Link: https://www.kaggle.com/datasets/yagunnersya/fifa-21-messy-raw-dataset-for-cleaning-exploring?select=fifa21_raw_data.csv%E2%80%8B

## Data Cleansing Process
1. Loading the Data
The dataset was loaded using pandas. There was a mixed data type warning for one of the columns due to inconsistencies, but the low-memory setting helped avoid further complications.
In my case I did not include low-memory setting.

df = pd.read_csv("fifa21.csv")

2. Removing Irrelevant Columns
The Loan Date End column, which was sparsely populated, was dropped as it was not relevant for the analysis.

df.drop('Loan Date End', axis=1, inplace=True)

3. Handling String Formatting
Height and Weight columns were stored as strings with units (e.g., "180cm", "75kg"). These were cleaned by removing the units and converting them into numeric values for proper analysis.

df['Height'] = df['Height'].str[:-2]
df['Weight'] = df['Weight'].str[:-2]

4. Handling Missing Values
Missing values were identified in several columns. Columns with a large proportion of missing data were either dropped or retained based on their importance for analysis.

5. Data Type Correction
The dataset contained columns with inconsistent data types (e.g., numeric columns stored as strings). These columns were converted to the appropriate data types for accurate analysis.

6. Data Summary
The cleaned dataset contains 18,979 players, and 77 attributes, after handling missing values and data cleaning operations.

## Tools that were used for this project:
Jupyter Notebook
Numpy
Pandas

# Next Step
The next step would be to perform exploratory data analysis and feature engineering as required for modelling process
