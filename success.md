---
layout: success
---
<script type="text/javascript" async
  src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.7/MathJax.js?config=TeX-MML-AM_CHTML">
</script>

# Decoding Movie Success

Welcome to the Success Score Page, where we unravel the secrets behind what makes a movie successful. Grab some popcorn and get ready to dive into the fascinating world of movie analytics!

## Understanding the Success Score

Ever wondered what factors contribute to a movie's success? We've got you covered! Our team has meticulously evaluated various features to create a Success Score that gauges the impact of elements such as:

- **Box Office Revenue**
- **Movie Release Year**
- **Ethnic Diversity Score**
- **Gender Diversity Score**
- **Adventure**
- **English Language**
- **Movie Runtime**
- **Indie**
- **World Cinema**
- **Action**
- **Drama**

### The Perfect Formula

To quantify success, we've devised a formula that takes into account essential features:

$$ \text{Success Score} = (\text{Box Office Revenue} - \text{Budget}) \times \text{Vote Average} $$

#### Justification:

- **Box Office Revenue - Budget:** The difference signifies the financial success of a movie, reflecting how much it earned beyond its production costs.
- **Vote Average:** This factor represents audience approval, a crucial aspect in determining a movie's overall success.

<div style="text-align: center; margin: 0 auto;">
  <!-- Replace the following line with your actual graph code -->
  <iframe src="assets/plots/Success_over_time.html" width="900" height="600" frameborder="0" style="display: block; margin: 0 auto;"></iframe>
</div>

## Unveiling the Machine Learning Model

Curious about predicting a movie's revenue? We've developed a cutting-edge machine learning model that relies on key features. The top influencers are:

1. **Budget:** The financial backbone of a movie.
2. **Movie Runtime:** Impactful in capturing audience attention.
3. **Movie Release Year:** Reflects the influence of time on a movie's success.
4. **Gender Diversity Score and Ethnic Diversity Score:** As significant as the 'Drama' category.

### Conclusion: Practicality Prevails

In all our analyses, a clear pattern emerges—practical features play a paramount role in determining a movie's box office success. The budget, movie runtime, release year, and genre, especially drama, weigh heavily in the equation.

## The Diversity Factor

Surprisingly, our research indicates that diversity factors, such as Ethnic and Gender Diversity Scores, don't emerge as primary influencers. While they hold importance, their impact is comparable to that of the Drama genre.

In a nutshell, the formula for a successful movie is a blend of financial prowess, audience approval, and a well-thought-out combination of practical features. So, filmmakers, take note of these insights as you embark on your cinematic journey! 🎬✨

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
            // Perform your logic here
            // For now, let's display a message with the input values
            var message = 'Predicting with Budget: ' + budget + ', Release Year: ' + releaseYear;
            // Display the result message
            document.getElementById('result').innerHTML = message;
        }
    </script>
  
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



