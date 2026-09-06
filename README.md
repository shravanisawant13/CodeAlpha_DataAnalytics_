# 📊 CodeAlpha Task 3 — Data Visualization

## 🇮🇳 Unemployment in India

This project is part of the **CodeAlpha Data Analytics Internship** and focuses on analyzing unemployment data in India using Python and data visualization techniques.

The objective is to transform raw unemployment data into meaningful visualizations that help identify **time-based trends, regional differences, Rural-Urban patterns, and relationships between numerical variables**.

---

## 🎯 Objective

The main objective of this project is to:

* Analyze unemployment trends over time
* Compare unemployment rates across different regions
* Compare unemployment between Rural and Urban areas
* Study the relationship between labour participation and unemployment
* Analyze correlations between numerical variables
* Present findings using clear and meaningful visualizations

---

## 📁 Dataset

The project uses the **Unemployment in India** dataset.

### Main columns used:

* `Region`
* `Date`
* `Area`
* `Estimated Unemployment Rate (%)`
* `Estimated Labour Participation Rate (%)`
* Other numerical variables available in the dataset

---

## 🛠️ Technologies & Libraries

* **Python**
* **Pandas** — Data manipulation and analysis
* **NumPy** — Numerical operations
* **Matplotlib** — Data visualization
* **Seaborn** — Statistical visualization
* **Jupyter Notebook**

---

## 🧹 Data Preprocessing

Before creating the visualizations, the dataset was prepared using the following steps:

1. Loaded the CSV dataset using Pandas
2. Removed extra spaces from column names
3. Removed missing values
4. Removed duplicate records
5. Converted the `Date` column into datetime format

```python
df.columns = df.columns.str.strip()
df = df.dropna()
df = df.drop_duplicates()
df['Date'] = pd.to_datetime(df['Date'], dayfirst=True)
```

---

# 📈 Visualizations

## 1. Unemployment Rate Over Time

A **line chart** was created to show the average unemployment rate in India over time.

### Purpose

* Identify increasing and decreasing unemployment periods
* Observe major fluctuations
* Understand overall time-based trends

```python
average_unemployment = (
    df.groupby('Date')['Estimated Unemployment Rate (%)']
    .mean()
    .reset_index()
)
```

**Key Insight:**
The line chart makes changes and fluctuations in the average unemployment rate over time easier to observe.

---

## 2. Average Unemployment Rate by Region

A **bar chart** was used to compare the average unemployment rate across different regions.

### Purpose

* Identify regional differences
* Compare unemployment rates between regions
* Find regions with relatively higher or lower unemployment

**Key Insight:**
The visualization shows considerable variation in unemployment rates across regions, indicating differences in employment conditions.

---

## 3. Rural vs Urban Unemployment

A **boxplot** was used to compare unemployment rate distributions between Rural and Urban areas.

### Purpose

* Compare central values
* Analyze the spread of unemployment rates
* Identify potential outliers
* Understand Rural-Urban differences

```python
sns.boxplot(
    data=df,
    x='Area',
    y='Estimated Unemployment Rate (%)'
)
```

**Key Insight:**
The boxplot helps compare the distribution, spread, and potential outliers of unemployment observations between Rural and Urban areas.

---

## 4. Unemployment Rate vs Labour Participation Rate

A **scatter plot** was created to examine the relationship between:

* Estimated Labour Participation Rate
* Estimated Unemployment Rate

### Purpose

* Identify possible relationships between the variables
* Observe the distribution of data points
* Identify unusual observations

```python
sns.scatterplot(
    data=df,
    x='Estimated Labour Participation Rate (%)',
    y='Estimated Unemployment Rate (%)'
)
```

**Key Insight:**
The scatter plot provides a visual understanding of whether labour participation and unemployment rates show a noticeable relationship.

---

## 5. Correlation Heatmap

A **correlation heatmap** was created to summarize relationships between numerical variables.

```python
correlation = df.corr(numeric_only=True)

sns.heatmap(
    correlation,
    annot=True,
    cmap='coolwarm',
    fmt='.2f'
)
```

### Purpose

* Identify strongly related numerical variables
* Identify weak relationships
* Understand linear associations between variables

**Note:**
Correlation shows association between variables and does not by itself prove causation.

---

# 📌 Key Questions Answered

This project addresses the following questions:

| Question                                                    | Visualization          |
| ----------------------------------------------------------- | ---------------------- |
| How has unemployment changed over time?                     | 📈 Line Chart          |
| Which regions have higher unemployment rates?               | 📊 Bar Chart           |
| How does unemployment differ between Rural and Urban areas? | 📦 Boxplot             |
| How are employment-related variables related?               | 🔵 Scatter Plot        |
| What relationships exist between numerical variables?       | 🔥 Correlation Heatmap |

---

# 🔍 Overall Insights

The visualizations provide a clear overview of unemployment patterns in India:

* Unemployment changes over time and shows noticeable fluctuations.
* Unemployment rates vary across different regions.
* Rural and Urban areas show differences in unemployment distributions.
* Labour participation and unemployment can be explored through their scatter relationship.
* The correlation heatmap provides an overview of relationships among numerical variables.

---

# 📂 Project Structure

```text
CodeAlpha_DataAnalytics_Data-Visualization/
│
├── CodeAlpha_DataAnalytics_Data Visualization.ipynb
├── Unemployment in India.csv
└── README.md
```

---

# ▶️ How to Run the Project

### 1. Clone the repository

```bash
git clone <your-repository-link>
```

### 2. Open the project directory

```bash
cd CodeAlpha_DataAnalytics_Data-Visualization
```

### 3. Install required libraries

```bash
pip install pandas numpy matplotlib seaborn jupyter
```

### 4. Start Jupyter Notebook

```bash
jupyter notebook
```

### 5. Open the notebook

Open:

```text
CodeAlpha_DataAnalytics_Data Visualization.ipynb
```

Make sure the **`Unemployment in India.csv`** dataset is placed in the same directory as the notebook.

---

# 📸 Visualizations

The project includes:

* 📈 Unemployment trend over time
* 📊 Regional unemployment comparison
* 📦 Rural vs Urban boxplot
* 🔵 Labour participation vs unemployment scatter plot
* 🔥 Numerical correlation heatmap

You can add screenshots of these visualizations to this README to make the GitHub repository more attractive.

---

# 🎓 Internship

**Program:** CodeAlpha Data Analytics Internship
**Task:** Task 3 — Data Visualization
**Project:** Unemployment in India

---

# 👩‍💻 Author

**Shravani**

B.Sc. Data Science Student

---

⭐ If you find this project useful, consider giving the repository a **star**!
