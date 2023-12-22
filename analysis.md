---
layout: analysis
---

# <span style="color: #9C3587;">Movie correlation Analysis</span>
## <span style="color: #9C3587;">Concept</span>
In this part of our project, we'll try to observe if the diversity seems to impact a movie's success. And if it isn't the case what are the other factors that do influence a movie outcome? In other words, we'll look at the correlations between the `Box office revenue` of the movies and their characteristics, such as the year of release, the genre, the cast or the budget.

## <span style="color: #9C3587;">Defining the success of a movie</span>
So, the aim is to  assess the success of movies depending on different factors. But _how_ do we define success? 

### <span style="color: #9C3587;">Box office revenue</span>
The first feature in our dataset that could quantify a movie's success is the `Box office revenue`. Indeed, it's usually true that the more successful a movie is, the more people will watch it in the theatres and generate revenue.

For our analysis, we also care about the temporal evolution of movie success and its features over time. Thus, for better comprehension, let's visualise the mean `Box office revenue` over time.

<div style="text-align: center; margin: 0 auto;">
  <iframe src="assets/plots/box_office_over_time.html" width="900" height="600" frameborder="0" style="display: block; margin: 0 auto;"></iframe>
</div>

We can see that the mean `Box office revenue` is increasing over time until ~2008. As mentionned before, the dataset might be less complete after 2008, leading to the revenue decrease.
The general revenue increase could be due to a lot of different factors:
- First, the revenue currency isn't the same as 100 hundred years ago. The revenue value entered in 1956 doesn't have the same impact or meaning as we have not adjusted for inflation.
- With time, more money is given to produce a movie 

***

## <span style="color: #9C3587;">Ethnic representation analysis</span>

### <span style="color: #9C3587;">Box office revenue depending on ethnic group</span>
We'll start by answering one of the first questions we could ask: Is there a difference in the `Box office revenue` depending on the ethnic group? 
Let's have a look at this!

<div style="text-align: center; margin: 0 auto;">
  <iframe src="assets/plots/revenue_per_ethnicity.html" width="900" height="600" frameborder="0" style="display: block; margin: 0 auto;"></iframe>
</div>

We see that actors of all ethnicities play on average in similarly lucrative movies. Our statistical analyses tell us, however, that white people tend to play in the movies with the highest box office revenues and Asian people in those with the lowest box office revenues. <br>

It could also be relevant to analyze how the mean box office revenue evolved.

<div style="text-align: center; margin: 0 auto;">
  <iframe src="assets/plots/box_office_ethnic_group_over_time.html" width="900" height="600" frameborder="0" style="display: block; margin: 0 auto;"></iframe>
</div>

All different ethnicities seem to follow the same general behaviour but _White_ actors still seem to play in movies which ended up with a higher revenue.


### <span style="color: #9C3587;">Ethnic Diversity Score</span>

For our analysis we wanted to define a variable that could quantify the diversity representation in movies. We first tried to use the number of unique ethnicities in movie but it didn't take into account the proportion of each ethnicity in the cast. For example, if a movie has 20 White, 1 Asian, 1 Middle Eastern and 1 Black actor, the score will be 4, as we have 4 different ethnicites. However, we can't say that this cast is diverse. We neeeded a more robust score.


The `Ethnic diversity score` is rooted in the idea that all ethnicities should be of equal percentage in the cast. We have 4 ethnic groups in our analysis, so each should make up 25% of the cast. In our calculation, we penalise the changes from this 25%. We then subtract the difference of each group from 1 ( whihc corresponds to 100%). When an ethnic group makes up the whole cast this approach would yield a score of -1. We then normalized to have a score range from 0 to 1. 

Let's consider the relations between this score and the `Box office revenue`. For now let's have a general overview of the score tendancy across time. 

<div style="text-align: center; margin: 0 auto;">
  <iframe src="assets/plots/mean_ethnic_diversity_score_over_time.html" width="900" height="600" frameborder="0" style="display: block; margin: 0 auto;"></iframe>
</div>

We see that this score tends to get higher as we get closer to current days. This is good news for the representation of everyone on the big screen. 

Now let's drive into a deeper analysis, by dividing the `Ethnic diversity score` into small range of 0.1. First let's see what kind of mean `Box office revenue` is associated with each range. 

<div style="text-align: center; margin: 0 auto;">
  <iframe src="assets/plots/box_office_dep_ethnic_diversity_score.html" width="900" height="600" frameborder="0" style="display: block; margin: 0 auto;"></iframe>
</div>

The general tendancy seems to be that the higher the `Ethnic diversity score` is the higher the `Box office revenue` is.  However the range [0.3,0.4] doesn't follow the general tendancy and has the highest mean revenue. The general tendancy of higher revenue with more diverse cast could be explain by the fact that both `Box office revenue` and `Ethnic diversity score` increases with time. 

Let's also check this distribution of each range over time.

<div style="text-align: center; margin: 0 auto;">
  <iframe src="assets/plots/ethnic_diversity_score_over_time.html" width="900" height="600" frameborder="0" style="display: block; margin: 0 auto;"></iframe>
</div>

Surpisingly the range between [0.2,0.3] and [0.4,0.5] are the most present diversity score distribution while they're also associated to very low `Box office revenue` (remember the previous figure). It means that the most common ethnic diversity representation setting (low-mid representation) doesn't lead to the most lucrative movie. Whereas some rare movies that have "the good" cast ethnic diversity ([0.3,0.4] low-mid score or [0.9,1] high score) may be related to the highest revenue. 


## <span style="color: #9C3587;">Gender representation analysis</span>

### <span style="color: #9C3587;">Box office revenue depending on the gender</span>
As mentionned before, our analysis is mostly focus on the diversity and thus gender representation also matters to us. Let's see the differences between men and women. In this following graph we might think that the mean `Box office revenue` is similar for both, but we want to highlight that the scale is logarithmic! Do not rely only on your eyes!

<div style="text-align: center; margin: 0 auto;">
  <iframe src="assets/plots/box_office_per_gender.html" width="900" height="600" frameborder="0" style="display: block; margin: 0 auto;"></iframe>
</div>

Not only is there a 4 million dollars gap between the medians, but a quick t-test confirms that this difference is statistically significant. Hence, women play in less lucrative movies. Hopefully, this might improve in the future.<br>

### <span style="color: #9C3587;">Gender Diversity Score</span>
We said scores, so here is our second score. We concentrate on the gender of the actors here and we penalise any under- or overrepresentation of gender similarly to our ethnic diversity score above. <br>

It's now time to see the evolution of this variable over time.

<div style="text-align: center; margin: 0 auto;">
  <iframe src="assets/plots/gender_diversity_score_over_time.html" width="900" height="600" frameborder="0" style="display: block; margin: 0 auto;"></iframe>
</div>

The growth on this graph is somewhat steeper than the one on the `Ethnic diversity score`. Starting with the mid to late 90s, the score has not gone below 0.5, but has also not gone much higher. Nonetheless, this seems like progress to us.

So how do movies do with respect to their `Gender diversity score`?

<div style="text-align: center; margin: 0 auto;">
  <iframe src="assets/plots/box_office_dep_gender_diversity_score.html" width="900" height="600" frameborder="0" style="display: block; margin: 0 auto;"></iframe>
</div>


A first glance at this graph shows that mostly low diversity scores have high box office revenues. Does that mean that when there are women in movies they bring down the revenues? No, not necessarily. It just means that the most popular movies until now had an unbalanced cast.



### <span style="color: #9C3587;">Genre</span>

We can also think about the genre of the movie we are talking about. Depending on the genre, people will be more or less likely to go to the cinema and so to contribute to the `Box office revenue`. We show here the **Top 10** most represented movie genres.

<div style="text-align: center; margin: 0 auto;">
  <iframe src="assets/plots/revenue_vs_genre.html" width="900" height="600" frameborder="0" style="display: block; margin: 0 auto;"></iframe>
</div>

We notice that Adventure movies are the most lucrative, along with Thrillers, while Indie and World Cinema movies are on the lowest sides. Indie movies tend less to be in cinema than other types of movies and World Cinema is usually less globalised. Thus, not many surprised here.


## <span style="color: #9C3587;">Correlation tables</span>
We use a machine learning tools to see if we can predict the `Box office revenue` value of a movie based on its characteristics, such as diversity, budget or genres. 

We divide this part in two, wanting to investigate if we could predict a success score without taking into account the budget of the movie. The main reason for this is that we have a limited amount of information about the budgets. This information coming from an external source, we only get information about 10% of our original data, which is a considerabale reduction that could lead to wrong conclusions.

<div style="text-align: center; margin: 0 auto;">
  <iframe src="assets/plots/corr_box_no_budget_color.html" width="900" height="600" frameborder="0" style="display: block; margin: 0 auto;"></iframe>
</div>
 

When looking at the analysis without taking the `Budget` in account, it seems that the most positively impacting factors are the genres `Adventure`and `Action`, and the movie characteristics `English language`, `Movie runtime` and `Movie_release_year`. On the other side, the negatively impacting factors are related to the movie genre. It appears that the actors characteristics don't really impact much the movie success compare to other factors. Interestingly  `Crime` is a genre that is highly variable on the impact on the `Box office revenue`. Also when looking at the $R^2$ value, we can see that the value is equal to 0.21 which is realtively decent for real data. It's not particullary high but real data is usually hard to predict (lot of factors, cofactors,...). A quick reminder that the $R^2$ quantify the variance of the data that can be explained.


<div style="text-align: center; margin: 0 auto;">
  <iframe src="assets/plots/corr_box_budget_color.html" width="900" height="600" frameborder="0" style="display: block; margin: 0 auto;"></iframe>
</div>

When taking in account the `Budget`, we are working with a drastically smaller dataset where it's harder to generalize but let's still analyse the results. On the global picture, the `Budget` is the factor that has the most effect on the `Box office revenue` and all other factors seem to have a negligeable impact compared to it. For this prediction, the $R^2$ value is higher than previously. The model explains approximately half of the variance. Adding the `Budget` seems to help predicting the revenue, however let's also remember that the data used with the `Budget` is smaller than without it.

We notice that in both figures, the features related to the diverstiy (`Ethnic diversity score` and `Gender diversity score`) have a correlation coefficient really close to 0, meaning that theit impact on the `Box office revenue` is really small and almost negligeable (especially for the situation where we take the budget into acccount).
One more time, it seems that the diversity has negligeable impact on the `Box office revenue` compared to other other factors, such as the movie genre or characteristics (language, runtime).
