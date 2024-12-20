# Diabetes Analysis Through Veggies and Fruits

This repository contains an analysis of diabetes prevalence based on vegetable and fruit consumption using Python. The dataset used is `diabetes_binary_health_indicators_BRFSS2015.csv`, and visualizations are created to highlight key insights.

## Features

- Data cleaning and exploration
- Correlation heatmap
- Pie charts comparing diabetes prevalence based on vegetable and fruit consumption
- Bar charts for frequency distribution

## Prerequisites

Before running the code, ensure you have the following Python libraries installed:

```bash
pip install pandas numpy seaborn matplotlib
```

## Dataset

The dataset `diabetes_binary_health_indicators_BRFSS2015.csv` contains binary indicators for diabetes and health-related behaviors.

## Code Overview

### 1. Importing Libraries

```python
import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
```

### 2. Loading and Exploring the Data

```python
df = pd.read_csv('diabetes_binary_health_indicators_BRFSS2015.csv')
```
```python
df.info()
df.describe()
missing_values = df.isnull().sum()
print(missing_values)
```
```python
df.describe()
```
```python
df.head()
```

### 3. Correlation Heatmap

```python
plt.figure(figsize=(20,10))
sns.heatmap(df.corr(), annot=True, cmap='coolwarm')
plt.title("Correlation of Features")
plt.show()
```

### 4. Analysis Based on Vegetable Consumption

#### Data Filtering

```python
hp = df['Veggies'] == 1
veggies = df[hp]
```

#### Pie Chart for Diabetes and Vegetable Consumption

```python
labels = ['DIABETES', 'NOT DIABETES']
sizes = [len(veggies[df.Diabetes_binary == 1]), len(veggies[df.Diabetes_binary == 0])]

colors = ['#FF7F7F', '#7FB3FF']
explode = (0.05, 0)

fig, ax = plt.subplots(figsize=(10, 8), dpi=80)
patches, texts, autotexts = ax.pie(
    sizes,
    explode=explode,
    labels=labels,
    colors=colors,
    autopct='%1.2f%%',
    pctdistance=0.75,
    startangle=140,
    textprops={'fontsize': 14, 'fontweight': 'bold', 'fontname': 'Poppins'},
    wedgeprops={'edgecolor': 'white', 'linewidth': 2}
)

plt.suptitle("Diabetes Through Veggies", fontname='Poppins', fontsize=24, fontweight='bold')
plt.title("Comparison of Vegetable Consumption and Diabetes", fontname='Poppins', fontsize=14, color='grey')
plt.show()
```
#### Data Filtering

```python
hp = df['Veggies'] == 0
veggies = df[hp]
```

#### Pie Chart for Diabetes and Vegetable Consumption

```python
labels = ['DIABETES', 'NOT DIABETES']
sizes = [len(veggies[df.Diabetes_binary == 1]), len(veggies[df.Diabetes_binary == 0])]

colors = ['#FF7F7F', '#7FB3FF']
explode = (0.05, 0)

fig, ax = plt.subplots(figsize=(10, 8), dpi=80)
patches, texts, autotexts = ax.pie(
    sizes,
    explode=explode,
    labels=labels,
    colors=colors,
    autopct='%1.2f%%',
    pctdistance=0.75,
    startangle=140,
    textprops={'fontsize': 14, 'fontweight': 'bold', 'fontname': 'Poppins'},
    wedgeprops={'edgecolor': 'white', 'linewidth': 2}
)

plt.suptitle("Diabetes Through Veggies", fontname='Poppins', fontsize=24, fontweight='bold')
plt.title("Comparison of Vegetable Consumption and Diabetes", fontname='Poppins', fontsize=14, color='grey')
plt.show()
```

### 5. Analysis Based on Fruit Consumption

#### Data Filtering

```python
ft = df['Fruits'] == 1
fruit = df[ft]
```

#### Pie Chart for Diabetes and Fruit Consumption

```python
labels = ['DIABETES', 'NOT DIABETES']
sizes = [len(fruit[df.Diabetes_binary == 1]), len(fruit[df.Diabetes_binary == 0])]

colors = ['#FF7F7F', '#7FB3FF']
explode = (0.05, 0)

fig, ax = plt.subplots(figsize=(10, 8), dpi=80)
patches, texts, autotexts = ax.pie(
    sizes,
    explode=explode,
    labels=labels,
    colors=colors,
    autopct='%1.2f%%',
    pctdistance=0.75,
    startangle=140,
    textprops={'fontsize': 14, 'fontweight': 'bold', 'fontname': 'Poppins'},
    wedgeprops={'edgecolor': 'white', 'linewidth': 2}
)

plt.suptitle("Diabetes Through Fruits", fontname='Poppins', fontsize=24, fontweight='bold')
plt.title("Comparison of Fruit Consumption and Diabetes", fontname='Poppins', fontsize=14, color='grey')
plt.show()
```

#### Data Filtering

```python
ft = df['Fruits'] == 0
fruit = df[ft]
```

#### Pie Chart for Diabetes and Fruit Consumption

```python
labels = ['DIABETES', 'NOT DIABETES']
sizes = [len(fruit[df.Diabetes_binary == 1]), len(fruit[df.Diabetes_binary == 0])]

colors = ['#FF7F7F', '#7FB3FF']
explode = (0.05, 0)

fig, ax = plt.subplots(figsize=(10, 8), dpi=80)
patches, texts, autotexts = ax.pie(
    sizes,
    explode=explode,
    labels=labels,
    colors=colors,
    autopct='%1.2f%%',
    pctdistance=0.75,
    startangle=140,
    textprops={'fontsize': 14, 'fontweight': 'bold', 'fontname': 'Poppins'},
    wedgeprops={'edgecolor': 'white', 'linewidth': 2}
)

plt.suptitle("Diabetes Through Fruits", fontname='Poppins', fontsize=24, fontweight='bold')
plt.title("Comparison of Fruit Consumption and Diabetes", fontname='Poppins', fontsize=14, color='grey')
plt.show()
```

### 6. Bar Charts for Frequency Distribution

#### Vegetable Consumption

```python
pd.crosstab(df.Veggies, df.Diabetes_binary).plot(
    kind="bar",
    figsize=(8, 6),
    color=["#FF7F7F", "#7FB3FF"],
    linewidth=1.2
)
plt.title("Diabetes Frequency Based on Vegetable Consumption", fontsize=16, fontweight="bold", fontname="Poppins")
plt.xlabel("Vegetable Consumption", fontsize=14, fontweight="bold", fontname="Poppins")
plt.ylabel("Frequency", fontsize=14, fontweight="bold", fontname="Poppins")
plt.tight_layout()
plt.show()
```

#### Fruit Consumption

```python
pd.crosstab(df.Fruits, df.Diabetes_binary).plot(
    kind="bar",
    figsize=(8, 6),
    color=["#FF7F7F", "#7FB3FF"],
    linewidth=1.2
)
plt.title("Diabetes Disease Frequency for Fruits", fontsize=16, fontweight="bold", fontname="Poppins")
plt.xlabel("Fruits", fontsize=14, fontweight="bold", fontname="Poppins")
plt.ylabel("Frequency", fontsize=14, fontweight="bold", fontname="Poppins")
plt.tight_layout()
plt.show()
```

## Results

- **Correlation Heatmap**: Displays relationships between features.
- **Pie Charts**: Visualize the proportion of diabetes cases based on vegetable and fruit consumption.
- **Bar Charts**: Show frequency distribution of diabetes cases for consumers and non-consumers of vegetables and fruits.

## Kaggle
- **Kaggle Dataset** : https://www.kaggle.com/datasets/alexteboul/diabetes-health-indicators-dataset
- **Kaggle Notebook** : https://www.kaggle.com/code/chiejuwonsfx/the-effect-of-vegetable-and-fruit-consumption


## License

This project is licensed under the MIT License. See the LICENSE file for details.

## Features

