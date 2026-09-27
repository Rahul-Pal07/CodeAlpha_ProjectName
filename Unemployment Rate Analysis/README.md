# Unemployment Rate Analysis in India 📊

## 📌 Project Overview

This project analyzes unemployment trends in India using Python, Pandas, NumPy, Matplotlib, and Seaborn.

The analysis focuses on unemployment rates across **28 Indian states/UTs**, with data divided into **Rural and Urban areas**, covering the period from **May 2019 to June 2020**.

The project includes data cleaning, exploratory data analysis (EDA), COVID-19 impact analysis, seasonal analysis, correlation analysis, and data visualization.

---

## 🎯 Objectives

The main objectives of this project are:

* Clean and prepare the raw unemployment dataset
* Explore unemployment data across Indian states/UTs
* Compare Rural and Urban unemployment
* Analyze unemployment trends over time
* Compare Pre-COVID and COVID periods
* Analyze the impact of COVID-19 on unemployment rates
* Identify monthly/seasonal patterns
* Study the relationship between unemployment and labour participation
* Visualize important findings using charts

---

## 📂 Dataset

**Dataset:** `Unemployment in India.csv`

The dataset contains information about:

* **Region** – State/UT
* **Date** – Monthly observation date
* **Frequency** – Monthly
* **Estimated Unemployment Rate (%)**
* **Estimated Employed**
* **Estimated Labour Participation Rate (%)**
* **Area** – Rural / Urban

### Dataset Coverage

* **Period:** May 2019 – June 2020
* **States/UTs:** 28
* **Areas:** Rural and Urban
* **Cleaned records:** 740
* **Original records:** 768, including 28 completely empty rows

---

## 🛠️ Technologies Used

| Technology       | Purpose                        |
| ---------------- | ------------------------------ |
| Python           | Programming and analysis       |
| Pandas           | Data cleaning and manipulation |
| NumPy            | Numerical operations           |
| Matplotlib       | Data visualization             |
| Seaborn          | Statistical visualization      |
| Jupyter Notebook | Development environment        |

---

## 🔄 Project Workflow

```text
Raw Dataset
     ↓
Data Loading
     ↓
Data Cleaning
     ↓
Data Exploration
     ↓
Feature Creation
     ↓
COVID-19 Period Classification
     ↓
Trend Analysis
     ↓
State & Area Analysis
     ↓
Correlation Analysis
     ↓
Data Visualization
     ↓
Insights
```

---

## 🧹 Data Cleaning

The following cleaning steps were performed:

* Removed unnecessary spaces from column names
* Removed completely empty rows
* Checked for missing values
* Removed duplicate records
* Removed extra spaces from text columns
* Converted the `Date` column to datetime format
* Created `Year`, `Month`, and `Month_Name` columns
* Removed the constant `Frequency` column
* Sorted the dataset by Region, Area, and Date

After cleaning, the dataset contains **740 records with no missing values** in the analyzed columns.

---

## 📊 Exploratory Data Analysis

The project explores:

### 1. Dataset Structure

* Number of rows and columns
* Data types
* Missing values
* Summary statistics
* Number of states/UTs
* Rural and Urban categories

### 2. Unemployment Trends

The national average unemployment rate is analyzed month-by-month to understand how unemployment changed over the study period.

### 3. Rural vs Urban Analysis

The project compares unemployment rates between:

* Rural areas
* Urban areas

This helps identify differences in unemployment trends between the two area types.

---

## 🦠 COVID-19 Impact Analysis

A COVID period was created using **25 March 2020** as the reference date for the beginning of the nationwide lockdown.

```python
covid_date = pd.Timestamp("2020-03-25")

df["Period"] = np.where(
    df["Date"] >= covid_date,
    "Covid",
    "Pre-Covid"
)
```

The analysis compares:

* Pre-COVID unemployment
* COVID-period unemployment
* State-level changes
* Rural vs Urban changes

The change in unemployment rate is calculated as:

```text
COVID Average - Pre-COVID Average
```

---

## 📈 Visualizations

The project creates several visualizations.

### 1. National Unemployment Trend

Shows the change in India's average unemployment rate over time.

### 2. Rural vs Urban Unemployment

Compares unemployment trends between Rural and Urban areas.

### 3. COVID Impact by State

Shows the states with the largest changes in unemployment rate between the Pre-COVID and COVID periods.

### 4. State vs Month Heatmap

A heatmap is used to compare unemployment rates across states and months.

### 5. Seasonal Pattern

Shows the average unemployment rate by calendar month.

### 6. Labour Participation vs Unemployment

A scatter plot is used to examine the relationship between:

* Labour Participation Rate
* Unemployment Rate

### 7. Average Unemployment by State

Shows the average unemployment rate for each state/UT during the complete study period.

---

## 📁 Project Structure

```text
Unemployment-Rate-Analysis/
│
├── Unemployment Rate Analysis.ipynb
├── Unemployment in India.csv
├── Unemployment_in_India_cleaned.csv
├── state_covid_impact.csv
│
├── 01_national_trend.png
├── 02_rural_vs_urban.png
├── 03_state_covid_impact.png
├── 04_state_month_heatmap.png
├── 05_seasonality.png
├── 06_lpr_vs_unemployment.png
├── 07_state_average.png
│
└── README.md
```

---

## 🔍 Key Analysis Performed

### Unemployment Rate

The project calculates average unemployment rates using:

```python
df.groupby("Region")[
    "Estimated Unemployment Rate (%)"
].mean()
```

### COVID Impact

State-level COVID impact is calculated by comparing:

```text
COVID Average − Pre-COVID Average
```

### Correlation

The relationship between unemployment and labour participation is measured using Pandas correlation:

```python
correlation = df[
    [
        "Estimated Labour Participation Rate (%)",
        "Estimated Unemployment Rate (%)"
    ]
].corr().iloc[0, 1]
```

---

## 💡 Skills Demonstrated

This project demonstrates practical skills in:

* Python
* Pandas
* NumPy
* Data Cleaning
* Data Preprocessing
* Exploratory Data Analysis
* GroupBy
* Aggregation
* Pivot Tables
* Date & Time Analysis
* Correlation Analysis
* Data Visualization
* Matplotlib
* Seaborn
* Business/Data Insights

---

## ▶️ How to Run the Project

### 1. Clone the repository

```bash
git clone https://github.com/Rahul-Pal07/CodeAlpha_ProjectName/tree/main/Unemployment%20Rate%20Analysis
```

### 2. Open the project

Open the project folder in:

* Jupyter Notebook
* JupyterLab
* VS Code

### 3. Install required libraries

```bash
pip install pandas numpy matplotlib seaborn
```

### 4. Open the notebook

```text
Unemployment Rate Analysis.ipynb
```

### 5. Run the cells

Run the notebook cells from top to bottom.

Make sure the CSV file is in the same project folder as the notebook.

---

## 📌 Conclusion

This project provides an exploratory analysis of unemployment in India from **May 2019 to June 2020**, with particular focus on state-level differences, Rural vs Urban trends, monthly patterns, and the change observed around the COVID-19 period.

The project demonstrates an end-to-end **Data Analyst workflow**, starting from raw data cleaning and ending with analysis, visualization, and export of cleaned datasets.

---

## 👨‍💻 Author

**Rahul Pal**

BCA Graduate | Data Science Trainee | Aspiring Data Analyst

**Skills:** Python | SQL | Pandas | NumPy | Excel | Power BI | Data Analysis | Data Visualization

---

## ⭐ If you find this project useful

Feel free to ⭐ the repository and explore the notebook.
