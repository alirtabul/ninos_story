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

Have you ever wondered what factors contribute to a movie's success? We've got you covered! Our team has evaluated various features to create a Success Score until reaching the **Perfect Formula** (hope so). This formula takes into account essential features in the following manner:

$$ \text{Success Score} = (\text{Box Office Revenue} - \text{Budget}) \times \text{Vote Average} $$

#### Justification:

- **Box Office Revenue - Budget:** The difference signifies the financial success of a movie, reflecting how much it earned beyond its production costs.
- **Vote Average:** This factor represents audience approval, a crucial aspect in determining a movie's overall success.

Below you can find the evolution of this success score over time. As it is possible to see, the score has fluctuations over the years, but on average there is a slight increase. This variable seems to capture the behavior of its componants. The `Success score` appears to have the variations of the `Vote average` while also having the increase of the `Box office revenue` and the `Budget`.

<div style="text-align: center; margin: 0 auto;">
  <!-- Replace the following line with your actual graph code -->
  <iframe src="assets/plots/Success_over_time.html" width="800" height="900" frameborder="0" style="display: block; margin: 0 auto;"></iframe>
</div>

The movies with the highest success are the following:

<div style="text-align: center; margin: 0 auto;">
  <img src="assets/plots/Most_successful_movies.png" style="width: 100%; height: auto; display: block; margin: 0 auto;">
</div>

## Unveiling the Machine Learning Models

Once the ML models have been trained and evaluated we can see the influence that their features had thanks to the Shapley values. 

Shapley values, in the context of our cinematic analysis, serve as illuminating metrics to discern the individual impact of each feature on predicting a movie's success. Imagine a collaborative project where each member's contribution is recognized and valued. Similarly, Shapley values assign credit to each feature, considering its unique role in shaping the overall prediction. 

By calculating Shapley values, we gain insights into the relative importance of factors like budget, movie runtime, genre, release year, and ethnic diversity, understanding how each contributes to the cinematic triumph. It's akin to acknowledging the distinct notes in a harmonious symphony, where each feature plays a crucial part in composing the narrative of a successful film.

Both models presented similar Shapley distributions however the model to predict the `Box office revenue` performed way ($R^2$ = ~0.4-0.6) better than `Success score` predictor ($R^2$ = ~0.2). Subsequently, you will only plot the results for the Box Office Revenue ML predictor:

<div style="text-align: center; margin: 0 auto;">
  <!-- Replace the following line with your actual graph code -->
  <iframe src="assets/plots/shap_summary_plot.html" width= 800 height=400 frameborder="0" style="display: block; margin: 0 auto;"></iframe>
</div>

The top influencers are: 

1. **Budget:** The financial backbone of a movie.
2. **Movie Runtime:** Impactful in capturing audience attention.
3. **Movie release year:** Reflect the economical situation.

The Ethnic Diversity score has no major influence on the decision of the model.

### Conclusion: Practicality Prevails

In all our analyses, a clear pattern emerges—practical features play an important role in determining a movie's box office success or predicting the success score. The budget, movie runtime, release year, and genre, especially drama, weigh heavily in the equation.

## The Diversity Factor

Surprisingly, our research indicates that diversity factors, such as Ethnic and Gender Diversity Scores, don't emerge as primary influencers.

So, filmmakers, take note of these insights as you embark on your cinematic journey! 🎬✨
