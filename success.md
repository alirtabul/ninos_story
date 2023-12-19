---
layout: success
---
<script type="text/javascript" async
  src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.7/MathJax.js?config=TeX-MML-AM_CHTML">
</script>

# Decoding Movie Success

Welcome to the Success Score Page, where we unravel the secrets behind what makes a movie successful. In our pursuit of understanding cinematic intricacies, we have developed two Machine-Learning models:

1. **Success Score Predictor:** This model endeavors to predict a tailored Success Score, a metric designed to encapsulate the holistic success of a movie.
2. **Revenue Predictor:** Our second model focuses on forecasting Box Office Revenue, a critical determinant of a movie's financial trajectory.

Bear in mind that the idea is to see if features related to ethnicity, have an impact on the predictions made by the models.  

## Understanding the Success Score

Have you ever wondered what factors contribute to a movie's success? We've got you covered! Our team has evaluated various features to create a Success Score until reaching the **Perfect Formula**. This formula takes into account essential features in the following manner:

$$ \text{Success Score} = (\text{Box Office Revenue} - \text{Budget}) \times \text{Vote Average} $$

#### Justification:

- **Box Office Revenue - Budget:** The difference signifies the financial success of a movie, reflecting how much it earned beyond its production costs.
- **Vote Average:** This factor represents audience approval, a crucial aspect in determining a movie's overall success.

Below you can find the evolution of this success score over time. As it is possible to see, the score has fluctuations over the years, but on average there is no notable increase. 

<div style="text-align: center; margin: 0 auto;">
  <!-- Replace the following line with your actual graph code -->
  <iframe src="assets/plots/Success_over_time.html" width="700" height="900" frameborder="0" style="display: block; margin: 0 auto;"></iframe>
</div>

The movies with the highest success are the following:

<div style="text-align: center; margin: 0 auto;">
  <img src="assets/plots/Most_successful_movies.png" style="width: 100%; height: auto; display: block; margin: 0 auto;">
</div>

## Unveiling the Machine Learning Models

Once the ML models have been trained and evaluated we can see the influence that their features had thanks to the Shapley values. Shapley values, in the context of our cinematic analysis, serve as illuminating metrics to discern the individual impact of each feature on predicting a movie's success. Imagine a collaborative project where each member's contribution is recognized and valued. Similarly, Shapley values assign credit to each feature, considering its unique role in shaping the overall prediction. By calculating Shapley values, we gain insights into the relative importance of factors like budget, movie runtime, genre, release year, and ethnic diversity, understanding how each contributes to the cinematic triumph. It's akin to acknowledging the distinct notes in a harmonious symphony, where each feature plays a crucial part in composing the narrative of a successful film.

Both models presented similar Shapley distributions. Subsequently, you can see the results for the Box Office Revenue ML predictor:

<div style="text-align: center; margin: 0 auto;">
  <!-- Replace the following line with your actual graph code -->
  <iframe src="assets/plots/shap_summary_plot.html" width= 600 height=300 frameborder="0" style="display: block; margin: 0 auto;"></iframe>
</div>

The top influencers are: 

1. **Budget:** The financial backbone of a movie.
2. **Movie Runtime:** Impactful in capturing audience attention.
3. **Making a Drama movie:** Reflects the influence of time on a movie's success.

The Ethnic Diversity score has no major influence on the decision of the model.

### Conclusion: Practicality Prevails

In all our analyses, a clear pattern emerges—practical features play an important role in determining a movie's box office success or predicting the success score. The budget, movie runtime, release year, and genre, especially drama, weigh heavily in the equation.

## The Diversity Factor

Surprisingly, our research indicates that diversity factors, such as Ethnic and Gender Diversity Scores, don't emerge as primary influencers.

In a nutshell, the formula for a successful movie is a blend of financial prowess and a well-thought-out combination of the aforementioned features. So, filmmakers, take note of these insights as you embark on your cinematic journey! 🎬✨

## Try the Models!

Make sure to check our official repository and try our ML predictors! 

You can try them as well below (This feature still is under revision as we are experiencing problems with the model deployment in a server.)

<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Success Score Predictor</title>
    <!-- Include the scikit-learn and joblib CDN -->
    <script src="https://cdn.jsdelivr.net/npm/scikit-learn@0.24.2/dist/scikit-learn.js"></script>
    <script src="https://cdn.jsdelivr.net/npm/joblib@0.16.0/dist/joblib.js"></script>
</head>
<body>
    <h1>Linear Regression Predictor</h1>
    <label for="budget">Budget:</label>
    <input type="number" id="budget" step="any" required>
    <br>
    <label for="releaseYear">Movie release year:</label>
    <input type="number" id="releaseYear" step="any" required>
    <br>
    <label for="ethnicScore">Ethnic Diversity Score:</label>
    <input type="number" id="ethnicScore" step="any" required>
    <br>
    <label for="genderScore">Gender Diversity Score:</label>
    <input type="number" id="genderScore" step="any" required>
    <br>
    <label for="adventure">Adventure:</label>
    <input type="number" id="adventure" step="any" required>
    <br>
    <label for="englishLanguage">English language:</label>
    <input type="number" id="englishLanguage" step="any" required>
    <br>
    <label for="runtime">Movie runtime:</label>
    <input type="number" id="runtime" step="any" required>
    <br>
    <label for="indie">Indie:</label>
    <input type="number" id="indie" step="any" required>
    <br>
    <label for="worldCinema">World cinema:</label>
    <input type="number" id="worldCinema" step="any" required>
    <br>
    <label for="action">Action:</label>
    <input type="number" id="action" step="any" required>
    <br>
    <label for="drama">Drama:</label>
    <input type="number" id="drama" step="any" required>
    <br>
    <button onclick="predict()">Predict</button>
    <p id="result"></p>
    <script>
        function predict() {
            // Get input values
            var budget = parseFloat(document.getElementById('budget').value);
            var releaseYear = parseFloat(document.getElementById('releaseYear').value);
            var ethnicScore = parseFloat(document.getElementById('ethnicScore').value);
            var genderScore = parseFloat(document.getElementById('genderScore').value);
            var adventure = parseFloat(document.getElementById('adventure').value);
            var englishLanguage = parseFloat(document.getElementById('englishLanguage').value);
            var runtime = parseFloat(document.getElementById('runtime').value);
            var indie = parseFloat(document.getElementById('indie').value);
            var worldCinema = parseFloat(document.getElementById('worldCinema').value);
            var action = parseFloat(document.getElementById('action').value);
            var drama = parseFloat(document.getElementById('drama').value);
            // Load your trained linear regression model
            var model = joblib.load('assets/plots/linear_regression_model.joblib');
            // Make prediction
            var prediction = model.predict([[budget, releaseYear, ethnicScore, genderScore, adventure, englishLanguage, runtime, indie, worldCinema, action, drama]]);
            // Display the result
            document.getElementById('result').innerHTML = 'Prediction: ' + 123;//prediction[0];
        }


      
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Linear Regression Predictor</title>
    <!-- Include the scikit-learn and joblib CDN -->
    <script src="https://cdn.jsdelivr.net/npm/scikit-learn@0.24.2/dist/scikit-learn.js"></script>
    <script src="https://cdn.jsdelivr.net/npm/joblib@0.16.0/dist/joblib.js"></script>
</head>
<body>
    <h1>Revenue Predictor</h1>
    <label for="budget">Budget:</label>
    <input type="number" id="budget" step="any" required>
    <br>
    <label for="releaseYear">Movie release year:</label>
    <input type="number" id="releaseYear" step="any" required>
    <br>
    <label for="ethnicScore">Ethnic Diversity Score:</label>
    <input type="number" id="ethnicScore" step="any" required>
    <br>
    <label for="genderScore">Gender Diversity Score:</label>
    <input type="number" id="genderScore" step="any" required>
    <br>
    <label for="adventure">Adventure:</label>
    <input type="number" id="adventure" step="any" required>
    <br>
    <label for="englishLanguage">English language:</label>
    <input type="number" id="englishLanguage" step="any" required>
    <br>
    <label for="runtime">Movie runtime:</label>
    <input type="number" id="runtime" step="any" required>
    <br>
    <label for="indie">Indie:</label>
    <input type="number" id="indie" step="any" required>
    <br>
    <label for="worldCinema">World cinema:</label>
    <input type="number" id="worldCinema" step="any" required>
    <br>
    <label for="action">Action:</label>
    <input type="number" id="action" step="any" required>
    <br>
    <label for="drama">Drama:</label>
    <input type="number" id="drama" step="any" required>
    <br>
    <button onclick="predict()">Predict</button>
    <p id="result"></p>
    <script>
        function predict() {
            // Get input values
            var budget = parseFloat(document.getElementById('budget').value);
            var releaseYear = parseFloat(document.getElementById('releaseYear').value);
            var ethnicScore = parseFloat(document.getElementById('ethnicScore').value);
            var genderScore = parseFloat(document.getElementById('genderScore').value);
            var adventure = parseFloat(document.getElementById('adventure').value);
            var englishLanguage = parseFloat(document.getElementById('englishLanguage').value);
            var runtime = parseFloat(document.getElementById('runtime').value);
            var indie = parseFloat(document.getElementById('indie').value);
            var worldCinema = parseFloat(document.getElementById('worldCinema').value);
            var action = parseFloat(document.getElementById('action').value);
            var drama = parseFloat(document.getElementById('drama').value);
            // Load your trained linear regression model
            var model = joblib.load('assets/plots/linear_regression_model.joblib');
            // Make prediction
            var prediction = model.predict([[budget, releaseYear, ethnicScore, genderScore, adventure, englishLanguage, runtime, indie, worldCinema, action, drama]]);
            // Display the result
            document.getElementById('result').innerHTML = 'Prediction: ' + 123;//prediction[0];
        }
    </script>
</body>
</html>



