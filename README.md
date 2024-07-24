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

# Read  the  file into  a  variable
tips_data = pd.read_csv(test_filepath)

# Print  the  first few  rows
print(tips_data.head())

# Print the last few rows
print(tips_data.tail())

# Print  the  data
tips_data

#seaborn Line plot
plt.figure(figsize=(10,  6))
sns.lineplot(data=tips_data,  x='total_bill',  y='tip',  hue='sex') 
plt.title('Line  Plot  of  Tip  Amount  vs.  Total  Bill  by  Gender') 
plt.xlabel('Total  Bill')
plt.ylabel('Tip') 
plt.show()

<img width="415" alt="image" src="https://github.com/user-attachments/assets/02b8e3d9-d5e8-4664-b3fc-94f094895200">

#Seaborn Heatmap
plt.figure(figsize=(10,  6))
pivot_table  =  tips_data.pivot_table(values='tip',  index='day',  columns='time',␣
↪aggfunc='mean')
sns.heatmap(pivot_table,  annot=True,  cmap='coolwarm') 
plt.title('Heatmap  of  Average  Tips  by  Day  and  Time') 
plt.show()

<img width="409" alt="image" src="https://github.com/user-attachments/assets/0f72cbf7-b1c4-4de1-9df0-4d4f1c9acf34">

#BarChart
plt.figure(figsize=(10,  6))
sns.barplot(data=tips_data,  x='day',  y='total_bill',  hue='sex') 
plt.title('Total  Bill  Amount  by  Day  and  Gender')
plt.show()

<img width="415" alt="image" src="https://github.com/user-attachments/assets/20f6b8b4-53e9-4bd6-964a-db29d30f628a">

#subset columns
subset  =  tips_data[['total_bill',  'tip',  'sex']] 
print(subset.head())

#Scatter Plots
plt.figure(figsize=(10,  6))
sns.scatterplot(data=tips_data,  x='total_bill',  y='tip',  hue='sex') 
plt.title('Scatter  Plot  of  Tip  Amount  vs.  Total  Bill  by  Gender') 
plt.show()

<img width="415" alt="image" src="https://github.com/user-attachments/assets/5cb35862-a4fc-4a5b-a0a1-6bd71f57555a">

#Color-Coded Scatter Plots
plt.figure(figsize=(10,  6))
sns.scatterplot(data=tips_data,  x='total_bill',  y='tip',  hue='smoker',␣
↪style='sex')
plt.title('Color-Coded  Scatter  Plot  of  Tip  Amount  vs.  Total  Bill  by  Smoker␣
↪Status  and  Gender') 
plt.show()

<img width="415" alt="image" src="https://github.com/user-attachments/assets/09f79d01-e7cd-4fe9-a093-3a6dd7b191e9">

#sns.lmplot (Linear Model Plot)
sns.lmplot(data=tips_data,  x='total_bill',  y='tip',  hue='sex',  aspect=1.5) 
plt.title('Linear  Model  Plot  of  Tip  Amount  vs.  Total  Bill  by  Gender') 
plt.show()

<img width="405" alt="image" src="https://github.com/user-attachments/assets/078e7a5d-f7bc-41f6-b585-fc15b71cf898">


#sns.swarmplot
plt.figure(figsize=(10,  6))
sns.swarmplot(data=tips_data,  x='day',  y='total_bill',  hue='sex') 
plt.title('Swarm  Plot  of  Total  Bill  Amount  by  Day  and  Gender') 
plt.show()

<img width="415" alt="image" src="https://github.com/user-attachments/assets/084b146b-b42d-443e-99fe-309baa855fb8">

#Histograms
plt.figure(figsize=(10,  6))
sns.histplot(data=tips_data,  x='total_bill',  kde=True,  hue='sex') 
plt.title('Histogram  of  Total  Bill  Amount  by  Gender')
plt.show()

<img width="414" alt="image" src="https://github.com/user-attachments/assets/e4f9e19b-0fbb-4c61-b753-fe8751b510a6">

#Density Plots
plt.figure(figsize=(10,  6))
sns.kdeplot(data=tips_data,  x='total_bill',  hue='sex',  fill=True) 
plt.title('Density  Plot  of  Total  Bill  Amount  by  Gender') 
plt.show()

<img width="413" alt="image" src="https://github.com/user-attachments/assets/fd1f16e3-fc15-4ece-a3fb-016af743a1b6">

#2D KDE Plots
plt.figure(figsize=(10,  6))
sns.kdeplot(data=tips_data,  x='total_bill',  y='tip',  hue='sex',  fill=True) 
plt.title('2D  KDE  Plot  of  Tip  Amount  vs.  Total  Bill  by  Gender')
plt.show()

<img width="415" alt="image" src="https://github.com/user-attachments/assets/c2bc9d17-bf4b-4384-88ba-6d8bd29fc35a">

#sns.histplot (Another Histogram Example)
plt.figure(figsize=(10,  6))
sns.histplot(data=tips_data,  x='tip',  kde=True,  hue='smoker') 
plt.title('Histogram  of  Tip  Amount  by  Smoker  Status') 
plt.show()

<img width="414" alt="image" src="https://github.com/user-attachments/assets/e0e12f4d-3112-41fc-b218-321e970e8702">

#pair plots 
sns.pairplot(tips_data,  hue="sex") 
plt.show()

<img width="408" alt="image" src="https://github.com/user-attachments/assets/87d1f3f4-d0ba-4694-bd1d-72bf710e9160">

#FacetGrid for Multiple Plots
g = sns.FacetGrid(tips_data,  col="sex",  height=6,  aspect=1) 
g.map(sns.histplot, "total_bill")
g.add_legend() 
plt.show()

<img width="405" alt="image" src="https://github.com/user-attachments/assets/a4fad8e9-6ec1-4c94-9a56-7f28de29d5ca">

# Violin  Plot
plt.figure(figsize=(10,  6))
sns.violinplot(data=tips_data,  x='day',  y='total_bill',  hue='sex',  split=True) 
plt.title('Violin  Plot  of  Total  Bill  by  Day  and  Gender')
plt.show()

<img width="408" alt="image" src="https://github.com/user-attachments/assets/ea6673f4-f06b-4ebb-a8c3-331d1fff2020">

# Box  Plot
plt.figure(figsize=(10,  6))
sns.boxplot(data=tips_data,  x='day',  y='total_bill',  hue='sex') 
plt.title('Box  Plot  of  Total  Bill  by  Day  and  Gender') 
plt.show()

<img width="415" alt="image" src="https://github.com/user-attachments/assets/beef7670-19b4-46c2-baa6-bce3c0a96151">

# Joint  Plot
sns.jointplot(data=tips_data,  x='total_bill',  y='tip',  kind='reg') 
plt.show()

<img width="407" alt="image" src="https://github.com/user-attachments/assets/c01924cf-34ad-4e72-b1f6-623e0db6de3b">

#Interactive  Visualizations  Using   Plotly 
# Interactive scatter plot
fig  =  px.scatter(tips_data,  x='total_bill',  y='tip',  color='sex',␣
↪title='Interactive  Scatter  Plot') fig.show()

# Interactive  box  plot
fig  =  px.box(tips_data,  x='day',  y='total_bill',  color='sex',␣
↪title='Interactive  Box  Plot') fig.show()

<img width="402" alt="image" src="https://github.com/user-attachments/assets/42272ee6-5122-4035-a93a-f6948501203a">

<img width="402" alt="image" src="https://github.com/user-attachments/assets/326c29e2-a87f-4014-bb91-56ba44679e0d">






