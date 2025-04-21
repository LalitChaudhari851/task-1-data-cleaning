# Task 1: Data Cleaning and Preprocessing

## Objective
The main goal of this task was to clean a dataset using Python and Pandas. I worked on handling missing values, removing duplicate entries, and fixing any formatting issues in the data.

## Dataset Used
I used the "Mall Customer Segmentation Data" which I got from Kaggle. It contains information like Customer ID, Gender, Age, Annual Income, and Spending Score.

## Tools Used
- Python
- Pandas library
- Jupyter Notebook

## Steps I Followed
1. First, I loaded the dataset using read_csv() in Pandas.
2. I cleaned up the column names by converting them to lowercase and replacing spaces with underscores.
3. I checked for and removed duplicate rows using .drop_duplicates().
4. I also checked for missing values using .isnull() and dropped the rows with missing data.
5. I cleaned the 'gender' column by converting all values to lowercase for consistency.
6. I checked the data types and made sure that numeric columns like 'age' are in the correct format (integer).
7. Finally, I saved the cleaned data into a new file called Cleaned_Mall_Customers.csv.

## Code Snippet Example
```python
import pandas as pd

df = pd.read_csv("Mall_Customers.csv")
df.columns = df.columns.str.strip().str.lower().str.replace(" ", "_")
df.drop_duplicates(inplace=True)
df.dropna(inplace=True)
df['gender'] = df['gender'].str.lower().str.strip()
df.to_csv("Cleaned_Mall_Customers.csv", index=False)
