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
            <p>This project explores how various factors influence recipe ratings. We analyze a dataset of recipe interactions, investigate feature importance, and build predictive models to estimate user ratings.</p>
        </section>

        <section id="dataset">
            <h2>Dataset</h2>
            <p>The dataset consists of recipes, user ratings, and metadata. Key features include:</p>
            <ul>
                <li>Number of ingredients</li>
                <li>Cooking time</li>
                <li>Steps involved</li>
                <li>Nutritional values</li>
            </ul>
        </section>

        <section id="methods">
            <h2>Methods</h2>
            <p>We implemented the following steps:</p>
            <ul>
                <li>Data preprocessing and cleaning</li>
                <li>Exploratory Data Analysis (EDA)</li>
                <li>Feature Engineering</li>
                <li>Predictive Modeling (Linear Regression, Random Forest, etc.)</li>
                <li>Fairness Analysis using statistical tests</li>
            </ul>
        </section>

        <section id="results">
            <h2>Results</h2>
            <p>Our best-performing model achieved an R² score of <strong>0.003</strong>, indicating challenges in predicting ratings from the available features.</p>
        </section>

        <section id="fairness">
            <h2>Fairness Analysis</h2>
            <p>We conducted a fairness analysis to check whether model performance varied across different groups (e.g., short vs. long prep time). A permutation test revealed no statistically significant bias.</p>
        </section>

        <section id="conclusion">
            <h2>Conclusion</h2>
            <p>Despite moderate predictive success, feature selection remains a challenge. Future work should explore additional metadata and user behaviors.</p>
            <p><a href="finalproject.pdf" class="btn btn-primary">Download Full Report</a></p>
        </section>
    </div>

    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/js/bootstrap.bundle.min.js"></script>
</body>
</html>
