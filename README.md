# **Recipe Ratings Analysis**

## **Introduction**
This project investigates the factors influencing recipe ratings and develops predictive models to estimate user ratings. The goal is to understand how features such as preparation time, number of ingredients, and cooking steps impact user ratings. We employ various data science techniques, including data preprocessing, exploratory data analysis (EDA), feature engineering, predictive modeling, and fairness analysis.

Understanding user preferences in online recipe ratings can provide valuable insights for recipe recommendation systems and food bloggers. However, predicting recipe ratings is a challenging task due to the subjective nature of taste and user behavior. This project aims to build a predictive model while also evaluating fairness in model performance across different recipe categories.

---

## **Data Cleaning and Exploratory Data Analysis**

### **Data Cleaning**
The dataset consists of two main components:
1. **Recipes Dataset**: Contains details about each recipe, including ingredients, preparation time, cooking steps, and nutritional information.
2. **Interactions Dataset**: Includes user ratings and interactions with the recipes.

#### **Key Cleaning Steps:**
- Replaced ratings of **zero** with NaN values to avoid misleading data.
- Handled missing values in key features such as description length.
- Standardized text-based features and ensured numerical features were properly formatted.

### **Univariate Analysis**
We conducted an analysis of individual features to understand their distribution:
- **Rating Distribution:** Most ratings cluster around high values, indicating a potential bias towards positive ratings.
- **Number of Ingredients:** Most recipes contain between 5 to 15 ingredients.
- **Cooking Time:** There is a long-tail distribution, with some recipes requiring extreme durations.

**Insert: Rating Distribution Plot**

### **Bivariate Analysis and Aggregations**
We examined relationships between key variables:
- **Correlation between cooking time and rating:** Found no strong correlation.
- **Analysis of recipe complexity (ingredient count) vs. rating:** More complex recipes do not necessarily receive higher ratings.
- **Grouping by cuisine type:** Some cuisines tend to receive higher ratings than others.

**Insert: EDA Visualizations**

---

## **Assessment of Missingness**

### **Addressing NMAR Question**
We investigated whether missing descriptions were **Not Missing at Random (NMAR)** by analyzing whether missing descriptions correlated with ratings. If certain types of recipes were systematically missing descriptions, this could introduce bias.

### **Permutation Tests for Missingness**
To formally test for missingness mechanisms, we performed permutation tests:
- Compared mean ratings between recipes with and without missing descriptions.
- **p-value = 0.003**, suggesting that missing descriptions are not completely random.

### **Interpreting Missingness Test Results**
- Since missing descriptions seem to be correlated with rating differences, imputing missing descriptions using average ratings or alternative methods may improve model robustness.

**Insert: Missingness Analysis Plots**

---

## **Hypothesis Testing**

### **Selected Hypothesis**
We formulated a hypothesis about the relationship between cooking time and rating:
- **Null Hypothesis (H₀):** The number of minutes required for a recipe does not impact the average rating.
- **Alternative Hypothesis (H₁):** Recipes with shorter cooking times have different average ratings than those with longer cooking times.

### **Test Statistic and Permutation Test**
- We used the **difference in means** as the test statistic.
- A permutation test was conducted by randomly shuffling cooking times and recalculating the mean difference.
- **p-value = 0.314**, meaning we fail to reject the null hypothesis.

### **Interpretation**
- There is no strong evidence that cooking time directly impacts user ratings.
- Other features (e.g., ingredient quality, cuisine) may be more important predictors.

**Insert: Hypothesis Testing Results**

---

## **Framing a Prediction Problem**
The objective is to predict recipe ratings based on available features, treating this as a **supervised regression problem**.

**Feature Selection:**
- **Number of ingredients**: Measures recipe complexity.
- **Cooking time (minutes)**: Assesses the effort required.
- **Number of steps**: Captures procedural complexity.

---

## **Baseline Model**
To establish a reference, we trained a **Linear Regression model** and evaluated its performance:

**Results:**
- **Mean Squared Error (MSE):** 1.7573
- **Mean Absolute Error (MAE):** 0.8932
- **R² Score:** 0.0030 (indicating weak predictive power)

### **Interpretation**
- The baseline model performed poorly, suggesting that the selected features do not strongly predict ratings.
- We explored additional features and more advanced models in the next step.

**Insert: Baseline Model Evaluation Table**

---

## **Final Model**
To improve performance, we implemented:
- **Feature Engineering:** Log transformation, quantile transformation, and text-based features.
- **Hyperparameter Tuning:** Used **GridSearchCV** for optimization.
- **Models Tested:** Linear Regression, Random Forest, and Gradient Boosting.

### **Best Model: Random Forest**
- **MSE:** 1.9214
- **MAE:** 0.8658
- **R² Score:** -0.0901 (still weak, but better MAE than baseline)

### **Interpretation**
- The model still struggles to predict ratings accurately.
- Additional metadata (e.g., user preferences) could improve results.

**Insert: Final Model Performance Comparison Table**

---

## **Fairness Analysis**

We assessed whether model performance was fair across different groups:

### **Preparation Time Category**
- **RMSE for Short Prep Time:** 4.43
- **RMSE for Long Prep Time:** 5.10
- **Permutation Test p-value:** 0.44 (No statistical bias found)

### **Ingredient Complexity**
- **RMSE for Simple Recipes:** 4.69
- **RMSE for Complex Recipes:** 4.61

### **Conclusion**
- No strong evidence of fairness concerns was found.
- However, future studies should incorporate additional fairness metrics.

**Insert: Fairness Analysis Plots**

---

## **Conclusion**
While our models provided insights, their predictive power remained limited. Key takeaways:
- **Cooking time and ingredient count were not strong predictors of ratings.**
- **Linear regression performed poorly, and even Random Forest struggled.**
- **Fairness tests did not reveal strong bias, but more refined fairness metrics may be needed.**

### **Future Improvements**
- Incorporate **text-based sentiment analysis** from recipe descriptions.
- Use **user interaction data** to personalize rating predictions.
- Experiment with **deep learning approaches (e.g., LSTMs for text analysis).**
