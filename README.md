# **Recipe Ratings Analysis**

## **Introduction**
This project investigates the factors influencing recipe ratings and develops predictive models for estimating user ratings. We apply various data science techniques, including data preprocessing, exploratory data analysis (EDA), feature engineering, predictive modeling, and fairness analysis.

## **Data Cleaning and Exploratory Data Analysis**
### **Cleaned Data**
- Ratings of zero were replaced with NaN values.
- Missing values in key features were handled appropriately.

### **Performed Univariate Analyses**
- Visualized rating distributions.
- Examined individual feature distributions, such as cooking time and ingredient count.

### **Performed Bivariate Analyses and Aggregations**
- Analyzed relationships between key features and ratings.
- Aggregated data based on categorical variables such as cuisine type.

**Insert: Rating Distribution Plot**

## **Assessment of Missingness**
### **Addressed NMAR Question**
- Assessed whether missing values in descriptions were Not Missing at Random (NMAR).

### **Performed Permutation Tests for Missingness**
- Used permutation tests to check if missing descriptions affected ratings.

### **Interpreted Missingness Test Results**
- Found no significant relationship between missing descriptions and ratings.

**Insert: Missingness Analysis Plots**

## **Hypothesis Testing**
### **Selected Relevant Columns for Hypothesis or Permutation Test**
- Chose cooking time as the primary factor affecting ratings.

### **Explicitly Stated a Null Hypothesis**
- Null Hypothesis: The number of minutes required for a recipe does not impact the average rating.

### **Explicitly Stated an Alternative Hypothesis**
- Alternative Hypothesis: Recipes with shorter cooking times have different average ratings than those with longer cooking times.

### **Performed a Hypothesis or Permutation Test**
- Conducted a permutation test comparing short and long preparation time recipes.

### **Used a Valid Test Statistic**
- Used the difference in means as the test statistic.

### **Computed a p-value and Made a Decision**
- p-value was **0.314**, meaning we fail to reject the null hypothesis.

**Insert: Hypothesis Testing Results**

## **Framing a Prediction Problem**
- Defined recipe rating prediction as a supervised learning regression problem.
- Selected `n_ingredients`, `minutes`, and `n_steps` as initial features.
- Justified feature selection based on EDA insights.

## **Baseline Model**
- Trained a **Linear Regression model** to establish a baseline.
- Evaluated model performance using **Mean Squared Error (MSE), Mean Absolute Error (MAE), and R² Score**.
- Results:
  - MSE: **1.7573**
  - MAE: **0.8932**
  - R²: **0.0030** (suggesting weak predictive power)

**Insert: Baseline Model Evaluation Table**

## **Final Model**
- Engineered new features: **log transformation, quantile transformation, text-based features**.
- Compared multiple models: **Linear Regression, Random Forest, Gradient Boosting**.
- Used **GridSearchCV** for hyperparameter tuning.
- Best model: **Random Forest** with improved performance.
- Results:
  - MSE: **1.9214**
  - MAE: **0.8658**
  - R²: **-0.0901** (still weak, but better MAE than the baseline)

**Insert: Final Model Performance Comparison Table**

## **Fairness Analysis**
- Evaluated fairness across different recipe categories:

### **Preparation Time Category**
- RMSE for Short Prep Time: **4.43**
- RMSE for Long Prep Time: **5.10**
- **Permutation Test p-value: 0.44** (No statistical bias found)

### **Ingredient Complexity**
- RMSE for Simple Recipes: **4.69**
- RMSE for Complex Recipes: **4.61**

- **Conclusion:** No significant fairness concerns were found in model predictions.

**Insert: Fairness Analysis Plots**

## **Conclusion**
While our models provided insights, their predictive power remained limited. Future improvements should include additional user behavior data, better feature engineering, and alternative modeling techniques.
