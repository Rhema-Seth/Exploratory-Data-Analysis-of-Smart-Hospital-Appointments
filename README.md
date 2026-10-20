
# Healthcare Patient Appointment Data Analysis

## 1. Abstract / Overview

This project focuses on analyzing healthcare patient appointment data using Python. The main objective is to identify patterns in patient appointments, understand patient demographics, analyze healthcare costs, and explore relationships between numerical and categorical variables.

The project includes data cleaning, preprocessing, Exploratory Data Analysis (EDA), correlation analysis, and data visualization to extract meaningful insights from the dataset.

## 2. Problem Statement

Healthcare organizations generate large amounts of data related to patient appointments, doctor experience, treatment costs, and patient satisfaction. Analyzing this data can help identify appointment trends, understand patient behavior, and explore relationships between different healthcare variables.

This project analyzes patient appointment data to discover useful patterns and relationships that can support data-driven decision-making.

## 3. Objectives

- Understand the structure and characteristics of the dataset.
- Clean and preprocess the data.
- Handle missing values, data types, and outliers.
- Perform numerical and categorical analysis.
- Analyze percentage distributions and descriptive statistics.
- Identify correlations between numerical variables.
- Visualize important patterns and relationships.
- Generate meaningful insights from the analysis.

## 4. Dataset Description

**Dataset Name:** Smart Healthcare Patient Appointment Dataset

**Dataset Source:** [Kaggle - Smart Healthcare Patient Appointment Dataset](https://www.kaggle.com/datasets/sonalshinde123/smart-healthcare-patient-appointment-dataset)

The dataset contains 2,706 rows and 19 columns describing patient demographics, appointment details, doctor experience, healthcare costs, and satisfaction scores.

The dataset was obtained from Kaggle. The original underlying data source has not been independently verified.

### Dataset Features

| Column | Description |
|---|---|
| patient_id | Unique patient identifier |
| age | Patient's age |
| gender | Patient's gender |
| city | Patient's city |
| bmi | Body Mass Index |
| chronic_disease | Chronic disease information |
| appointment_type | Type of appointment |
| department | Healthcare department |
| symptoms | Reported symptoms |
| severity_level | Severity of the patient's condition |
| doctor_experience_years | Doctor's experience in years |
| consultation_fee | Consultation charges |
| insurance | Insurance status |
| appointment_month | Month of appointment |
| appointment_status | Appointment outcome |
| satisfaction_score | Patient satisfaction rating |
| medicine_cost | Cost of medicines |
| lab_test_cost | Cost of laboratory tests |
| total_bill | Total healthcare bill |

## 5. Tools and Technologies Used

- **Python:** Data analysis and manipulation
- **Pandas:** Data cleaning and data manipulation
- **NumPy:** Numerical operations
- **Matplotlib:** Data visualization
- **Seaborn:** Statistical visualization
- **Google Colab:** Coding and project execution
- **GitHub:** Project documentation and version control

## 6. Data Cleaning and Preprocessing

The following preprocessing steps were performed to prepare the dataset for analysis.

### 6.1 Data Inspection

- Examined the number of rows and columns.
- Checked column names and data types.
- Identified missing values.
- Examined duplicate records.
- Generated descriptive statistics.

### 6.2 Handling Missing Values

Missing values in selected categorical columns were handled as follows:

- `city` and `chronic_disease`: Filled using the mode.
- `appointment_type` and `symptoms`: Filled with `"Unknown"`.

### 6.3 Standardizing Column Names

Column names were standardized to maintain consistency and simplify coding.

### 6.4 Data Type Conversion

- `patient_id` was converted to string.
- Cost-related columns were converted to numerical data types.
- `doctor_experience_years` was converted to integer where appropriate.
- Selected categorical values were standardized for consistent presentation.

### 6.5 Outlier Detection and Handling

The Interquartile Range (IQR) method was used to identify potential outliers in selected numerical columns:

- Age
- Doctor experience
- Consultation fee
- Total bill

The IQR was calculated using:

**IQR = Q3 - Q1**

Where:
- Q1 represents the first quartile.
- Q3 represents the third quartile.

The lower and upper bounds were calculated as follows:

- Lower Bound = Q1 - 1.5 × IQR
- Upper Bound = Q3 + 1.5 × IQR

Rows identified as outliers were removed according to the project's preprocessing rules. Related cost columns were considered together when applying the removal logic.

## 7. Exploratory Data Analysis (EDA)

Exploratory Data Analysis was performed to understand the distribution, composition, and relationships within the dataset.

### 7.1 Numerical Analysis

Descriptive statistics were calculated using `describe()` to examine:

- Mean
- Median
- Standard deviation
- Minimum and maximum values
- First and third quartiles

### 7.2 Grouped Analysis

Grouping and aggregation were used to compare average values and summarize data across categories.

### 7.3 Categorical Analysis

Categorical columns were examined to understand the distribution of gender, appointment type, insurance status, and appointment outcomes.

### 7.4 Distribution Analysis

The `describe()` function was used to understand the spread and distribution of numerical variables.

Key observations from the original dataset:

- Average patient age: Approximately 44.84 years.
- Average BMI: Approximately 24.09.
- Average doctor experience: Approximately 15.52 years.
- Average consultation fee: Approximately 608.10 dataset currency units.
- Average satisfaction score: Approximately 7.73 out of 10.

These statistics describe the original dataset before preprocessing that may have changed the row count or distributions.

### 7.5 Percentage Analysis

Percentage distributions were calculated using normalized value counts to identify the proportion of records in each category.

**Gender Distribution**
- Male: 50.22%
- Female: 49.78%

**Appointment Type Distribution**
- Scheduled: 54.40%
- Walk-in: 31.45%
- Emergency: 14.04%
- Unknown: 0.11%

**Insurance Distribution**
- Yes: 59.76%
- No: 40.24%

**Appointment Status Distribution**
- Completed: 82.74%
- No Show: 12.42%
- Cancelled: 4.84%

These percentages reflect the previously analyzed distributions and may change after preprocessing.

### 7.6 Correlation Analysis

Correlation analysis was performed using the `corr()` function to identify relationships between numerical variables.

| Variable Comparison | Correlation | Interpretation |
|---|---:|---|
| Medicine cost vs. total bill | +0.963 | Very strong positive relationship |
| Doctor experience vs. consultation fee | +0.942 | Very strong positive relationship |
| Lab test cost vs. total bill | +0.929 | Very strong positive relationship |
| Medicine cost vs. lab test cost | +0.795 | Strong positive relationship |
| Satisfaction score vs. total bill | +0.434 | Moderate positive relationship |
| Age vs. BMI | +0.027 | Very weak positive relationship |

**Key Insights:**

- Medicine cost and total bill showed a very strong positive relationship.
- Lab test cost and total bill also showed a very strong positive relationship.
- Doctor experience and consultation fee showed a very strong positive relationship.
- Age and BMI had almost no linear relationship in the analyzed data.

Correlation indicates association and does not establish causation.

## 8. Data Visualization

Data visualization was used to present the findings clearly and identify patterns in the dataset.

### 8.1 Univariate Analysis

Univariate analysis examines one variable at a time.

#### Histogram - Age Distribution

A histogram was used to understand the distribution of patient ages and identify the age groups represented in the dataset.

![Age Distribution](images/age_distribution.png)

#### Pie Chart - Gender Distribution

A pie chart was used to display the percentage distribution of male and female patients.

![Gender Distribution](images/gender_distribution.png)

### 8.2 Bivariate Analysis

Bivariate analysis examines the relationship between two variables.

#### Bar Chart - Appointment Status vs. Number of Patients

A bar chart was used to compare the number of completed, cancelled, and missed appointments.

![Appointment Status](images/appointment_status.png)

#### Scatter Plot - Medicine Cost vs. Total Bill

A scatter plot was used to examine the relationship between medicine expenses and total healthcare bills.

![Medicine Cost vs Total Bill](images/medicine_cost_vs_total_bill.png)

### 8.3 Time-Based Analysis

#### Line Chart - Monthly Appointment Trend

A line chart was used to analyze changes in appointment counts across the months represented in the dataset.

![Monthly Appointment Trend](images/monthly_appointment_trend.png)

### 8.4 Multivariate Analysis

Multivariate analysis examines multiple variables simultaneously.

#### Correlation Heatmap

A correlation heatmap was used to display relationships among numerical variables and identify strong and weak correlations.

![Correlation Heatmap](images/correlation_heatmap.png)

#### Box Plot - Total Bill Distribution

A box plot was used to examine the distribution of total bills and identify potential outliers. When only total bill is analyzed, the box plot is a univariate visualization.

![Total Bill Box Plot](images/total_bill_boxplot.png)


## 9. Key Findings

- The gender distribution was nearly balanced between male and female patients.
- Scheduled appointments accounted for the largest appointment-type category.
- Most appointments were completed, while a smaller proportion were missed or cancelled.
- Approximately 59.76% of records indicated insurance coverage.
- Medicine cost had a very strong positive relationship with total bill.
- Lab test cost also showed a very strong positive relationship with total bill.
- Doctor experience and consultation fee showed a very strong positive relationship.
- Age and BMI showed almost no linear correlation.
- Satisfaction score had a moderate positive correlation with total bill.

These findings describe associations in the dataset and should not be interpreted as proof of causation.

## 10. Conclusion

This project demonstrates the application of Python-based data analysis to a healthcare patient appointment dataset.

Through data cleaning, preprocessing, EDA, correlation analysis, and visualization, the project identifies patterns in patient appointments, healthcare costs, patient demographics, and satisfaction scores.

The analysis provides useful insights into the dataset and demonstrates how data analytics can help explore healthcare operations and patient-related information.

The findings are exploratory and should not be interpreted as clinical conclusions or evidence of causation.

## 11. Limitations

- The original underlying data source has not been independently verified.
- The dataset may not represent all healthcare facilities or patient populations.
- Relationships may be influenced by variables not included in the dataset.
- Correlation does not establish causation.
- Results depend on data quality and preprocessing decisions.

## 12. Future Improvements

- Develop an interactive dashboard using Power BI.
- Perform deeper analysis of appointment cancellations and no-shows.
- Explore factors associated with patient satisfaction.
- Analyze department-wise appointment patterns and healthcare expenses.
- Build a predictive model for appointment no-shows, subject to suitable data and validation.
- Use verified real-world healthcare datasets for further investigation.

## 13. Project Structure

```text
healthcare-patient-appointment-analysis/
│
├── README.md
├── healthcare_patient_appointment_analysis.ipynb
├── dataset.csv
└── images/
    ├── age_distribution.png
    ├── gender_distribution.png
    ├── appointment_status.png
    ├── monthly_appointment_trend.png
    ├── medicine_cost_vs_total_bill.png
    ├── total_bill_boxplot.png
    └── correlation_heatmap.png
```

## 14. Author

**Rhema Mary Seth**

Aspiring Data Analyst 

**Areas of Interest:** Data Analytics, Healthcare Analytics, Data Visualization, and Business Intelligence

