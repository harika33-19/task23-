# task23-
# Value Counts and Frequency Analysis

## Overview
This project analyzes categorical columns in a dataset using Python and Pandas. It calculates category frequencies, proportions, and percentages, and visualizes important categorical distributions.

## Objectives
- Understand categorical data distributions.
- Count occurrences of unique categories.
- Calculate proportions and percentage distributions.
- Visualize categorical frequencies using bar charts.
- Interpret the results.

## Tools Used
- Python
- Pandas
- Matplotlib
- Google Colab or Jupyter Notebook

## Dataset
This project uses a small sample student dataset with five categorical columns:
- `Department`
- `Gender`
- `Result`
- `City`
- `Course`

You can replace the sample data with a real dataset such as Titanic or Iris.

## Steps
1. Import Pandas and Matplotlib.
2. Create or load the dataset.
3. Inspect the dataset and check missing values.
4. Use `value_counts()` to count categories in at least five categorical columns.
5. Use `value_counts(normalize=True)` to calculate proportions.
6. Multiply proportions by 100 to calculate percentages.
7. Create frequency tables.
8. Visualize category counts with bar charts.
9. Write a short interpretation of the results.

## Example Code

```python
import pandas as pd
import matplotlib.pyplot as plt

data = {
    "Department": ["CSE", "ECE", "CSE", "IT", "CSE"],
    "Gender": ["Male", "Female", "Female", "Male", "Female"],
    "Result": ["Pass", "Pass", "Pass", "Fail", "Pass"],
    "City": ["Hyderabad", "Guntur", "Hyderabad", "Vijayawada", "Guntur"],
    "Course": ["Python", "Java", "Python", "SQL", "Python"]
}

df = pd.DataFrame(data)

categorical_columns = ["Department", "Gender", "Result", "City", "Course"]

for column in categorical_columns:
    print(f"\nFrequency of {column}:")
    print(df[column].value_counts())

    print(f"\nPercentage distribution of {column}:")
    print((df[column].value_counts(normalize=True) * 100).round(2))

df["Department"].value_counts().plot(
    kind="bar",
    title="Department Frequency",
    xlabel="Department",
    ylabel="Count"
)
plt.tight_layout()
plt.show()
```

## Sample Findings
Based on the sample five-row dataset:
- CSE is the most common department, accounting for 60%.
- Female students account for 60%, and male students account for 40%.
- 80% of students passed, while 20% failed.
- Python is the most selected course, accounting for 60%.

These findings describe only the sample dataset and may differ when using another dataset.

## Key Pandas Functions
- `value_counts()` — counts occurrences of each unique value.
- `value_counts(normalize=True)` — returns proportions.
- `value_counts(normalize=True) * 100` — returns percentages.
- `plot(kind="bar")` — creates a bar chart.

## Conclusion
Value counts and frequency analysis help summarize categorical data, identify the most common categories, and communicate distributions through tables and charts.
