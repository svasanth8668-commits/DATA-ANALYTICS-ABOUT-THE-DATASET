# DATA-ANALYTICS-ABOUT-THE-DATASET

# AIM

To perform data analytics on a given dataset using Python and Pandas, understand the characteristics of the dataset, identify different types of data, examine missing values, and prepare the dataset for further analysis and machine learning.

# THEORY

Data analytics is the process of collecting, cleaning, transforming, and analysing data to discover useful information and patterns. Python is widely used for data analytics because it provides powerful libraries such as Pandas, NumPy, Matplotlib, and Seaborn.

Pandas is a Python library used to work with structured data in rows and columns. A dataset can be loaded into a Pandas DataFrame from files such as CSV, Excel, or JSON.

The main steps in dataset analysis are:

1. Load the dataset using `pd.read_csv()` or a suitable Pandas function.
2. Display records using `head()` and `tail()`.
3. Check the number of rows and columns using `shape`.
4. Examine column names and data types using `info()` and `dtypes`.
5. Generate descriptive statistics using `describe()`.
6. Identify missing values using `isnull().sum()`.
7. Handle missing values using `dropna()` or `fillna()`.
8. Identify duplicate records using `duplicated().sum()`.
9. Clean and prepare the dataset for analysis, visualization, and machine learning.

Data may be numerical, categorical, textual, date/time, or boolean. Numerical data can be continuous or discrete, while categorical data represents groups or labels.

# PYTHON PROGRAM

```python
import pandas as pd

# Load the dataset
df = pd.read_csv("dataset.csv")

# Display first five rows
print(df.head())

# Dataset dimensions
print("Dataset shape:", df.shape)

# Column names
print("Columns:", df.columns.tolist())

# Data types and non-null values
print(df.info())

# Statistical summary
print(df.describe())

# Missing values
print("Missing values:")
print(df.isnull().sum())

# Duplicate records
print("Duplicate rows:", df.duplicated().sum())

# Remove duplicate rows
df = df.drop_duplicates()

# Fill missing numerical values with the mean
numeric_columns = df.select_dtypes(include="number").columns
df[numeric_columns] = df[numeric_columns].fillna(df[numeric_columns].mean())

# Save cleaned dataset
df.to_csv("cleaned_dataset.csv", index=False)

print("Dataset cleaning completed successfully.")
