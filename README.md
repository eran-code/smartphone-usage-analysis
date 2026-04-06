# Smartphone Usage and Productivity Analysis

## Project Overview

This project analyzes the relationship between smartphone usage and productivity across 50,000 users. It examines how daily habits — including screen time, sleep, stress, and caffeine intake — influence work performance and well-being.

The analysis was conducted using Python in a Jupyter Notebook, covering data cleaning, exploratory data analysis, feature engineering, and correlation analysis.

---

## Objectives

- Examine how smartphone usage affects productivity
- Analyze the relationship between sleep, stress, and work performance
- Identify patterns across different user groups (age, occupation, device type)
- Practice real-world data cleaning and analysis on a large dataset

---

## Dataset

The dataset contains **50,000 records** with 13 features related to user behavior and lifestyle.

**File:** `Smartphone_Usage_Productivity_Dataset_50000.xlsx.csv`

| Column | Description |
|--------|-------------|
| User_ID | Unique identifier per user |
| Age | Age of the user |
| Gender | Male / Female / Other |
| Occupation | Student, Professional, Freelancer, Business Owner |
| Device_Type | Android or iOS |
| Daily_Phone_Hours | Average daily phone usage in hours |
| Social_Media_Hours | Hours spent on social media per day |
| Work_Productivity_Score | Productivity score out of 10 |
| Sleep_Hours | Average hours of sleep per night |
| Stress_Level | Stress score out of 10 |
| App_Usage_Count | Number of apps used daily |
| Caffeine_Intake_Cups | Cups of caffeine consumed per day |
| Weekend_Screen_Time_Hours | Screen time on weekends in hours |

---

## Tools and Libraries

| Tool | Purpose |
|------|---------|
| Python 3.11 | Core programming language |
| Pandas | Data manipulation and analysis |
| NumPy | Numerical operations |
| Matplotlib | Data visualization |
| Seaborn | Statistical plots and pairplots |
| Scikit-learn | Encoding and scaling |
| Jupyter Notebook | Development environment |

---

## Project Structure

```
smartphone-usage-analysis/
│
├── analysis.ipynb                                    # Main notebook
├── Smartphone_Usage_Productivity_Dataset_50000.xlsx.csv  # Raw dataset
├── README.md                                         # Project documentation
```

---

## Setup Instructions

### 1. Clone the repository

```bash
git clone https://github.com/your-username/smartphone-usage-analysis.git
cd smartphone-usage-analysis
```

### 2. Install required libraries

```bash
pip install pandas numpy matplotlib seaborn scikit-learn jupyter
```

### 3. Launch Jupyter Notebook

```bash
jupyter notebook
```

### 4. Open and run the notebook

Open `analysis.ipynb` and run all cells from top to bottom using **Run All** or step through each cell manually.

---

## Notebook Structure

The notebook is divided into 4 parts:

**Part 1 — Data Exploration**
- Loaded dataset using `pd.read_csv()`
- Checked shape, data types, and summary statistics using `.shape`, `.info()`, `.describe()`
- Identified 2,500 missing values in `Stress_Level` (5% of data)

**Part 2 — Data Cleaning and Transformation**
- Filled numeric missing values with column mean using `df.fillna()`
- Verified and removed duplicate rows using `drop_duplicates()`
- Detected outliers using the IQR method and capped them with `.clip()` instead of removing rows
- Encoded categorical columns using `pd.get_dummies()`
- Scaled numeric features using `StandardScaler`

**Part 3 — Exploratory Data Analysis (EDA)**
- Generated a pairplot on a 1,000-row sample to visualize relationships
- Computed and ranked correlations between all numeric features
- Key finding: all correlations are weak (below 0.10), suggesting no single factor strongly predicts productivity on its own

**Part 4 — Feature Engineering**
- Created `Usage_per_App` — average daily phone hours per app used
- Created `Sleep_Deficit` — difference between actual sleep and the recommended 8 hours
- Applied 10% random sampling and memory optimization (dtype downcasting)

---

## Key Insights

- Higher stress levels are associated with lower productivity scores
- Reduced sleep negatively impacts work performance
- Smartphone usage patterns vary across occupations
- All variable correlations are weak, suggesting productivity is influenced by a combination of factors rather than any single one
- Caffeine intake and weekend screen time show small but present correlations with stress

---

## Conclusion

This project walked through a full data analysis pipeline on 50,000 smartphone user records. The cleaning process handled intentionally introduced missing values, removed duplicates, and capped outliers. The EDA revealed that no single lifestyle variable is a strong predictor of productivity, which points toward the need for multi-feature modeling in future work.

---

## Acknowledgment

Dataset sourced from Kaggle. Implementation, preprocessing, and analysis were performed independently as part of academic practice.

