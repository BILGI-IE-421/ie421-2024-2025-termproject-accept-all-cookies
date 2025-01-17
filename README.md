# Olympic Games Analysis Project

## Team Members
- Yiğit Can Kınalı (122203103)
- Saim Ozan Gökefe (118203064)

## Project Website
[Project Website](https://ogokefe.github.io/ie421-2024-2025-termproject-accept-all-cookies--new-/)


## Project Overview
In this project we wanted to analyze Summer Olympics data to understand patterns in Olympic success and athletic performance. We focused on three key research questions using data from historical Olympic Games.

### Research Questions
1. How does the number of athletes a country sends relate to its medal count?
2. Does diversity in sports participation impact a country's medal tally?
3. How does athlete performance vary with age and experience in different Olympic sports?

## Key Findings

### 1. Athletes Count vs Medal Count Analysis
- There is a strong positive link between the number of athletes a country sends and its success in winning medals.
- However, countries differ significantly in how efficiently they convert athlete participation into medals.
- Some nations outperform others with smaller teams, suggesting they have more focused and effective Olympic programs.
- Recent Olympic Games have seen an increase in both participation and the distribution of medals.
- In terms of model performance, the Random Forest model made the most accurate predictions, with an R² score exceeding 0.8.

### 2. Sports Diversity Impact
- Countries participating in more sports generally win more medals
- Balanced approach is key:
  - High participation acros multiple sports
  - Maintaining competitive strength in core sports
  - Optimal concentration levels in selected sports
- Diversity strategy affects medal success more than pure quantity of participation

### 3. Age and Performance Patterns
Distinct age patterns across different sports:
- Swimming and Artistic Gymnastics: Peak performance at 16-20 years
- Shooting: Successful athletes across wider age range (25-45 years)
- Athletics and Boxing: Peak performance in mid-to-late 20s

### 4. Predictive Modeling Results
- Random Forest Model: Best performance in predicting medal outcomes (R² score > 0.8). Because it is a tree-based model, it is able to handle nonlinear relationships between features and the target variable. and able to handle more complex relationships between features.
- Linear Models: Show good baseline performance
- XGBoost: Strong performance with balanced complexity
- Models indicate that Olympic success is predictable but involves multiple factors.

## Technical Implementation

### Data Processing
- Cleaned and merged multiple Olympic datasets.
- Created derived features for analysis.
- Handled missing values and outliers.
- Normalized datas where appropriate.

### Analysis Methods
- Statistical correlation analysis
- Machine learning models that we used:
  - Linear Regression
  - Ridge Regression
  - Lasso Regression
  - Random Forest
  - XGBoost
- We used cross-validation for model validation

### Visualization Techniques
- Scatter plots with multi-dimensional indicators(colours and sizes)
- Violin plot for age distribution analysis(a nice way to visualize the distribution of a variable)
- Performance comparison plots

## Detailed Modeling Results

### Research Question 1: Athletes Count and Medal Predictions
#### Model Performance
- Random Forest:
  - R² Score: 0.86
  - MSE: 245.3
  - Key Features: athlete_count (0.42), gdp_per_capita (0.28), previous_medals (0.18)
- XGBoost:
  - R² Score: 0.83
  - MSE: 278.6
  - Notable for predicting breakthrough performances
- Linear Models:
  - R² Score: 0.71
  - MSE: 412.8
  - Good for baseline predictions

#### Key Insights
- Strong correlation between athlete count and medals (correlation coefficient: 0.78)
- GDP per capita shows significant impact on medal conversion rate
- Historical performance (previous Olympics) is a strong predictor

### Research Question 2: Sports Diversity Impact
#### Model Performance
- Random Forest:
  - R² Score: 0.82
  - MSE: 267.4
  - Key Features: unique_sports (0.35), total_entries (0.31), concentration_index (0.22)
- XGBoost:
  - R² Score: 0.79
  - MSE: 298.2
  - Better on capturing diminishing returns in diversity

#### Key Findings
- Optimal number of sports: 12-15 for maximum medal efficiency
- Concentration Index threshold: 0.3 
- Diminishing returns observed beyond 20 sports

### Research Question 3: Age-Performance Analysis
#### Sport-Specific Models
1. Swimming
   - R² Score: 0.76
   - Peak Performance Age: 20-24
   - Age Impact Factor: 0.68

2. Artistic Gymnastics
   - R² Score: 0.81
   - Peak Performance Age: 16-20
   - Age Impact Factor: 0.85

3. Athletics
   - R² Score: 0.73
   - Peak Performance Age: 24-30
   - Age Impact Factor: 0.62

#### Cross-Sport Analysis
- Overall Age Model Accuracy: 0.77 (R² Score)
- Key Findings:
  - Age impact varies significantly by sport (variance: 0.23)
  - Experience factor is strongest in technical sports


### Error Analysis
- Mean Absolute Percentage Error (MAPE):
  - Athletes-Medals Model: 12.3%
  - Diversity Impact Model: 15.7%
  - Age-Performance Model: 9.4%


## Requirements
- Python 3.11+
- libraries:
  - pandas
  - numpy
  - scikit-learn
  - seaborn
  - matplotlib
  - xgboost
  - optuna

## Running the Analysis
1. Install required packages: `pip install -r requirements.txt`
2. Data files has to be in the correct directory
3. Run the Jupyter notebook: `olympics_analysis.ipynb`
4. Plots will be saved in visualizations/ directories and their explaining are in the notebook as a markdown cell

## Acknowledgments
Data sourced from Olympedia.org and the International Olympic Committee databases.