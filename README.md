# recipe-ratings_analysis
DSC80 Final Project
# **Recipe Ratings Analysis**

## **Introduction**
This project investigates the factors influencing recipe ratings and develops predictive models for estimating user ratings. We apply various data science techniques, including data preprocessing, exploratory data analysis (EDA), feature engineering, predictive modeling, and fairness analysis.

## **Dataset**
The dataset consists of two key components:
- **Recipes**: Contains recipe details such as ingredients, preparation time, cooking steps, and nutritional information.
- **Interactions**: User reviews and ratings associated with each recipe.

### **Data Cleaning**
- Ratings of zero were replaced with NaN values.
- Missing values in key features were handled appropriately.

## **Methods**

### **1. Data Preprocessing**
- Handled missing values and outliers.
- Extracted relevant features such as cooking time, number of ingredients, and recipe complexity.

### **2. Exploratory Data Analysis (EDA)**
- Visualized rating distributions.
- Analyzed relationships between features and ratings.

**Insert: Rating Distribution Plot**

### **3. Feature Engineering**
- Extracted text-based features (e.g., recipe description length).
- Created categorical features based on cooking time and ingredient complexity.

### **4. Predictive Modeling**
We trained and evaluated multiple models:
- **Linear Regression**: Simple model for baseline comparison.
- **Decision Tree**: Captures non-linear relationships.
- **Random Forest**: Ensemble method improving model performance.

**Insert: Model Performance Comparison Table**

## **Results**
### **Model Performance**
| Model            | R²    | MSE    |
|-----------------|-------|--------|
| Linear Regression | 0.0030 | 1.7573 |
| Decision Tree    | -0.3455 | 2.3716 |
| Random Forest   | -0.0901 | 1.9214 |

None of the models performed significantly better than the baseline, indicating a challenge in predicting ratings with available features.

## **Fairness Analysis**
We evaluated model fairness across different recipe categories:

### **1. Preparation Time**
- RMSE for Short Prep Time: **4.43**
- RMSE for Long Prep Time: **5.10**
- Permutation Test p-value: **0.44** (No statistical bias found)

### **2. Ingredient Complexity**
- RMSE for Simple Recipes: **4.69**
- RMSE for Complex Recipes: **4.61**

**Insert: Fairness Analysis Plots**

## **Conclusion**
While our models provided insights, their predictive power remained limited. Future improvements should include additional user behavior data, better feature engineering, and alternative modeling techniques.
