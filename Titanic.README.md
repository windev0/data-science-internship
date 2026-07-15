# Titanic Survival Analysis – Data Cleaning & Exploratory Analysis

## Project Overview

This project focuses on the preparation and analysis of the Titanic passenger dataset. The objective was to clean the data, handle missing values, and perform an initial exploratory analysis to identify key factors influencing passenger survival.

The project demonstrates a complete data preparation workflow, from dataset inspection to cleaning decisions and first analytical insights.

## Data Cleaning Process

An initial exploration was performed using `shape`, `info()`, and `describe()` to understand the dataset structure, data types, and missing values.

### Missing Values Handling

- **Cabin column removal**:  
  The `Cabin` feature was removed because it contained **687 missing values out of 891 observations (~77%)**. With such a high level of missingness, imputing values would have introduced unreliable assumptions and potential bias.

- **Age column completion**:  
  The **177 missing values** in the `Age` column were replaced using the **median**.  
  The age distribution is slightly right-skewed, meaning the mean could be affected by extreme values from older passengers. The median provides a more robust estimation of the typical passenger age.

- **Embarked column completion**:  
  The **2 missing values** in the `Embarked` column were filled using the **mode**, which is the most suitable approach for categorical variables.

After cleaning, the dataset contained **no remaining missing values**, making it ready for further exploratory analysis and machine learning tasks.

## Initial Insights

The cleaned dataset contains:

- **891 passengers**
- **11 features**
- **0 missing values**

### Survival Analysis

- Total survivors: **342 passengers**
- Non-survivors: **549 passengers**
- Overall survival rate: **38.4%**

### Key Findings

**Gender impact**
- Female survival rate: **74.2%**
- Male survival rate: **18.9%**

Gender appears to be one of the strongest factors associated with survival.

**Passenger class impact**
- 1st Class survival rate: **63.0%**
- 2nd Class survival rate: **47.3%**
- 3rd Class survival rate: **24.2%**

Higher passenger classes were associated with higher survival probabilities, suggesting a strong relationship between socio-economic status and survival.

**Passenger demographics**
- Average age: **29.4 years**
- Age range: **0–80 years**
- Average fare: **$32.20**

The age distribution shows that most passengers were young adults (around 20–30 years old), with fewer older passengers, confirming the relevance of using the median for missing age imputation.

## Next Steps

The cleaned dataset will be used for further **Exploratory Data Analysis (EDA)**, including:
- Feature correlation analysis
- Data visualization
- Survival pattern investigation
- Feature engineering
- Preparation for predictive modeling