# Restaurant Tips Analysis

## Overview
This project analyzes a dataset of restaurant tips to uncover patterns and insights in tipping behavior. Various factors such as total bill amount, gender, smoking status, day of the week, and time of meal are examined to understand their impact on tipping.

## Dataset
The dataset used in this analysis is 'tips.csv', which contains the following columns:
- total_bill: Total bill amount
- tip: Tip amount
- sex: Gender of the bill payer
- smoker: Whether the party included smokers
- day: Day of the week
- time: Time of the meal (lunch or dinner)
- size: Number of people in the party

## Tools and Libraries
- Python 3.x
- pandas
- matplotlib
- seaborn
- plotly
- statsmodels
- scipy
- scikit-learn

## Key Visualizations
1. Line Plot: Tip Amount vs. Total Bill by Gender
2. Heatmap: Average Tips by Day and Time
3. Bar Chart: Total Bill Amount by Day and Gender
4. Scatter Plots: Tip Amount vs. Total Bill (various versions)
5. Linear Model Plot: Tip Amount vs. Total Bill by Gender
6. Swarm Plot: Total Bill Amount by Day and Gender
7. Histograms and Density Plots: Distribution of Total Bill and Tip Amounts
8. Pair Plots: Relationships between multiple variables
9. Violin and Box Plots: Distribution of Total Bill by Day and Gender

## Key Findings
1. Positive correlation between total bill size and tip amount
2. Slight differences in tipping patterns between genders
3. Day of the week significantly affects total bill amounts
4. Party size is a significant factor in determining tip amounts
5. Smoking status and meal time may influence tipping behavior

## How to Run
1. Clone this repository
2. Install required packages: `pip install -r requirements.txt`
3. Open and run the Jupyter notebook in the `notebooks/` directory

