# assignment-7.py
python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns

# Task 1: Load and Explore the Dataset
# Load the dataset
df = pd.read_csv('your_dataset.csv')

# Display the first few rows
print(df.head())

# Check the data types and missing values
print(df.info())

# Clean the dataset
df = df.dropna()  # or use df.fillna() for filling missing values

# Task 2: Basic Data Analysis
# Compute basic statistics
print(df.describe())

# Group by a categorical column and compute the mean of a numerical column
grouped = df.groupby('category_column')['numerical_column'].mean()
print(grouped)

# Task 3: Data Visualization

# Line chart
plt.figure(figsize=(10, 6))
plt.plot(df['time_column'], df['numerical_column'])
plt.title('Trends Over Time')
plt.xlabel('Time')
plt.ylabel('Value')
plt.show()

# Bar chart
plt.figure(figsize=(10, 6))
sns.barplot(x='category_column', y='numerical_column', data=df)
plt.title('Comparison of Values Across Categories')
plt.xlabel('Category')
plt.ylabel('Average Value')
plt.show()

# Histogram
plt.figure(figsize=(10, 6))
plt.hist(df['numerical_column'], bins=20)
plt.title('Distribution of Numerical Column')
plt.xlabel('Value')
plt.ylabel('Frequency')
plt.show()

# Scatter plot
plt.figure(figsize=(10, 6))
plt.scatter(df['numerical_column1'], df['numerical_column2'])
plt.title('Relationship Between Two Numerical Columns')
plt.xlabel('Numerical Column 1')
plt.ylabel('Numerical Column 2')
plt.show()

