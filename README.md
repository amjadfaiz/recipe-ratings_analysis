# recipe-ratings_analysis
DSC80 Final Project
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Final Project - Recipe Ratings Analysis</title>
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css">
    <style>
        body { padding-top: 60px; }
        .container { max-width: 900px; }
    </style>
</head>
<body>
    <nav class="navbar navbar-expand-lg navbar-dark bg-dark fixed-top">
        <div class="container">
            <a class="navbar-brand" href="#">Recipe Ratings Analysis</a>
            <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav">
                <span class="navbar-toggler-icon"></span>
            </button>
            <div class="collapse navbar-collapse" id="navbarNav">
                <ul class="navbar-nav ms-auto">
                    <li class="nav-item"><a class="nav-link" href="#introduction">Introduction</a></li>
                    <li class="nav-item"><a class="nav-link" href="#dataset">Dataset</a></li>
                    <li class="nav-item"><a class="nav-link" href="#methods">Methods</a></li>
                    <li class="nav-item"><a class="nav-link" href="#results">Results</a></li>
                    <li class="nav-item"><a class="nav-link" href="#fairness">Fairness</a></li>
                    <li class="nav-item"><a class="nav-link" href="#conclusion">Conclusion</a></li>
                </ul>
            </div>
        </div>
    </nav>

    <div class="container">
        <section id="introduction">
            <h2>Introduction</h2>
            <p>This project investigates the factors influencing recipe ratings and develops predictive models for estimating user ratings. We apply various data science techniques, including data preprocessing, exploratory data analysis (EDA), feature engineering, predictive modeling, and fairness analysis.</p>
        </section>

        <section id="dataset">
            <h2>Dataset</h2>
            <p>The dataset consists of two key components:</p>
            <ul>
                <li><strong>Recipes:</strong> Contains recipe details such as ingredients, preparation time, cooking steps, and nutritional information.</li>
                <li><strong>Interactions:</strong> User reviews and ratings associated with each recipe.</li>
            </ul>
            <p><strong>Data Cleaning:</strong> Ratings of zero were replaced with NaN values, and missing values in key features were handled.</p>
        </section>

        <section id="methods">
            <h2>Methods</h2>
            <p>We implemented a step-by-step approach for data analysis and model building:</p>
            <h3>1. Data Preprocessing</h3>
            <p>- Handled missing values and outliers.<br>- Extracted relevant features such as cooking time, number of ingredients, and recipe complexity.</p>
            
            <h3>2. Exploratory Data Analysis (EDA)</h3>
            <p>- Visualized rating distributions.<br>- Analyzed relationships between features and ratings.</p>
            <p><em>Insert: Rating Distribution Plot</em></p>
            
            <h3>3. Feature Engineering</h3>
            <p>- Extracted text-based features (e.g., recipe description length).<br>- Created categorical features based on cooking time and ingredient complexity.</p>
            
            <h3>4. Predictive Modeling</h3>
            <p>We trained and evaluated multiple models:</p>
            <ul>
                <li><strong>Linear Regression:</strong> Simple model for baseline comparison.</li>
                <li><strong>Decision Tree:</strong> Captures non-linear relationships.</li>
                <li><strong>Random Forest:</strong> Ensemble method improving model performance.</li>
            </ul>
            <p><em>Insert: Model Performance Comparison Table</em></p>
        </section>

        <section id="results">
            <h2>Results</h2>
            <p><strong>Model Performance:</strong></p>
            <ul>
                <li>Linear Regression: R² = 0.0030, MSE = 1.7573</li>
                <li>Decision Tree: R² = -0.3455, MSE = 2.3716</li>
                <li>Random Forest: R² = -0.0901, MSE = 1.9214</li>
            </ul>
            <p>None of the models performed significantly better than the baseline, indicating a challenge in predicting ratings with available features.</p>
        </section>

        <section id="fairness">
            <h2>Fairness Analysis</h2>
            <p>We evaluated model fairness across different recipe categories:</p>
            <h3>1. Preparation Time</h3>
            <p>- RMSE for Short Prep Time: 4.43<br>- RMSE for Long Prep Time: 5.10<br>- Permutation Test p-value: 0.44 (No statistical bias found)</p>
            
            <h3>2. Ingredient Complexity</h3>
            <p>- RMSE for Simple Recipes: 4.69<br>- RMSE for Complex Recipes: 4.61</p>
            <p><em>Insert: Fairness Analysis Plots</em></p>
        </section>

        <section id="conclusion">
            <h2>Conclusion</h2>
            <p>While our models provided insights, their predictive power remained limited. Future improvements should include additional user behavior data, better feature engineering, and alternative modeling techniques.</p>
            <p><a href="finalproject.pdf" class="btn btn-primary">Download Full Report</a></p>
        </section>
    </div>

    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/js/bootstrap.bundle.min.js"></script>
</body>
</html>

