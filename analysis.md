---
layout: analysis
---

# Correlation Analysis
## Concept
Let us now take look at the correlations between the _Box office revenue_ of the movies and other factors. We will also give the _Vote average_ its time to shine.

### Number of ethnic groups present in the movie
First, since our analysis is about diversity, we will look at the influence of the number of ethnic groups present. Does it appear beneficial to have multiple ethnic groups?

![Movie revenue depending on the number of ethnic groups](/assets/img/movie_revenue_per_num_groups.png)

Looking at this graph, and by our analyses, we can see that the more ethnic groups are present the higher the box office revenue! We see that there is a positive correlation between the two. However, we also notice that the uncertainty of the income also becomes greater.

<div style="text-align: center; margin: 0 auto;">
  <iframe src="assets/plots/movies_pergroup_over_time.html" width="400" height="300" frameborder="0" style="display: block; margin: 0 auto;"></iframe>
</div>

Over the years, more and more movies are produced (and introduced in our data set), so more diverse movie are made. We notice, nonetheless, that movies with all four ethnic groups present are the rarest. 

<div style="text-align: center; margin: 0 auto;">
  <iframe src="assets/plots/box_office_over_time.html" width="400" height="300" frameborder="0" style="display: block; margin: 0 auto;"></iframe>
</div>

We also see that the box office revenue is also growing as time passes. The question is still there: Do the ethnicities of the cast influence in any way this growing of revenue?

<div style="text-align: center; margin: 0 auto;">
  <iframe src="assets/plots/revenue_per_ethnicity.html" width="900" height="600" frameborder="0" style="display: block; margin: 0 auto;"></iframe>
</div>

We see that actors of all ethnicity play on average in similarly lucrative movies. Our statistical anlyses tell us however that white people tend to play in the movies with highest box office revenues, while Asian people tend to play in the thos with the lowest box office revenues. <br>

However, one must keep in mind that these analyses are of correlation and not of causation, so choosing a majoritarily white cast will not guarantee in any way the success of a movie, nor will an asian cast bring misfortune upon the box offices.<br>

Let us also look at the _Vote average_.

![Movie revenue depending on the ethnic score](/assets/img/vote_avg_per_group.png)

This time we observe a slight negative correlation between the number of ethnic groups and the vote average. There is also a bigger uncertainty on the movies having all ethnic groups. The differences are only significant when looking at groups 1 and 3 as well as groups 1 and 4, otherwise the mixity does not impact much.

<div style="text-align: center; margin: 0 auto;">
  <iframe src="assets/plots/vote_avg_per_group.html" width="900" height="600" frameborder="0" style="display: block; margin: 0 auto;"></iframe>
</div>

The average votes of all ethnic groups are similar, with white people taking once again the lead. In this case, we don't particularly see a big difference.


### Diversity Scores
You will think, is the number of ethnic groups really what matters in diversity? What if there are is just one actor for diversity points? Well fear not! We had the same thoughts and we came up with what we call diversity scores! We created two of them, one focusing on ethnic diversity and a second focusing on gender diversity.

#### Ethnic Diversity Score
We penalise any over- or underrepresentation of ethnic groups in our calculations. Best score is 1 and worst score is 0. Now, let's see the relations between this score and the _Box office revenue_.

We see that this score tends to get higher as we get closer to current days. This is good news for the representation of everyone on the big screen. 

<div style="text-align: center; margin: 0 auto;">
  <iframe src="assets/plots/ethnic_diversity_score_over_time.html" width="900" height="600" frameborder="0" style="display: block; margin: 0 auto;"></iframe>
</div>

We must highlight though that the mean score never goes over 0.5 in the timeframe we were given, which is a bummer.<br>

In this next graph we will look at the mean box office revenue with respect to the ethnic diversity score.

![Movie revenue depending on the ethnic score](/assets/img/box_office_per_ethnic_score.png)

Once again we have a slight growing tendency of the revenue as the score grows. This can be proven by correlation tests, even if visually it does not seem to be the case. 

<br> Time for _Vote average_.

![Vote average depending on the ethnic score](/assets/img/vote_avg_per_ethnicscore.png)

Just like for the number of ethnic groups, we have a slight negative correlation.


#### Gender Diversity Score
We said scores, so here is our second score. We concenrate on the gender of the actors here and we penalise any under- or overrepresentation of gender similarly to our ethnic diversity score above. <br>

Before we give oour attention to the score, let us see the differences between men and women. In this following grpah we might think that the mean box office revenue is similar for both, but we want to highlight that the scale is logarithmic! Do not rely only on your eyes!

<div style="text-align: center; margin: 0 auto;">
  <iframe src="assets/plots/box_office_per_gender.html" width="900" height="600" frameborder="0" style="display: block; margin: 0 auto;"></iframe>
</div>

Not only is there a 4 million dollars gap between the medians, but a quick t-test confirms that this difference is statistically significant. Hence, women play in less well-payed movies. Hopefully, this might improve in the future.<br>

I say in the future, because lo and behold, our mean _Gender diversity score_ is getting higher as we advance towards present days!

<div style="text-align: center; margin: 0 auto;">
  <iframe src="assets/plots/gender_diversity_score_over_time.html" width="900" height="600" frameborder="0" style="display: block; margin: 0 auto;"></iframe>
</div>

The growth on this graph is somewhat steeper than the one on the _Ethnic diversity score_. Starting with the mid to late 90s, the score has not gone below 0.5, but has also not gone much higher. Nonetheless, this seems like progress to us.

So how do movies do with respect to their _Gender diversity score_?

![Movie revenue depending on the gender score](/assets/img/box_office_per_gender_score.png)

A first glance at this graph shows that mostly low diversity scores have high box office revenues. Does that mean that when there are women in movies they bring down the revenues? No, of course not. It just means that the most popular movies until now had less women, which is not so surprising. Our _Gender diversity score_ also only takes into account the presence of women, not their usefullness to the plot, but this is getting out of the scope of our research. If you are intereset in this topic we invite you to look up the <a href="https://en.wikipedia.org/wiki/Bechdel_test">Bechdel test</a>.


Unsurprisingly, the same categories shine when it comes to the _Vote average_ too.

![Movie revenue depending on the gender score](/assets/img/vote_avg_per_genderscore.png)

A slight negative correlation is present.


### Genre

We can also think about the genre of the movie we are talking about. Depending on the genre, people will be more or less likely to go to the cinema and so to contribute to the _Box office revenue_. We show here the **Top 10** most represented movie genres.

<div style="text-align: center; margin: 0 auto;">
  <iframe src="assets/plots/revenue_vs_genre.html" width="900" height="600" frameborder="0" style="display: block; margin: 0 auto;"></iframe>
</div>

We notice that Adventure movies are the most lucrative, along with Thrillers, while Indie and World Cinema movies are on the lowest sides. Indie movies tend less to be in cinema than other types of movies and World Cinema is usually less globalised. Thus, not many surprised here.

The _Vote average_ of each of these genres is interesting to look at too.

<div style="text-align: center; margin: 0 auto;">
  <iframe src="assets/plots/vote_avg_genre.html" width="900" height="600" frameborder="0" style="display: block; margin: 0 auto;"></iframe>
</div>

The tables have turned! Musicals and World cinema are the best rated genres, while Adventure and Thrillers find themselves toward the bottom of the list.

## Correlation tables

We will only focus on the _Box office revenue_ for the correlation tables. We divide this part in two, wanting to investigate if we could predict a success score without taking into account the budget of the movie.

<div style="text-align: center; margin: 0 auto;">
  <iframe src="assets/plots/corr_box_no_budget_color.html" width="900" height="600" frameborder="0" style="display: block; margin: 0 auto;"></iframe>
</div>

As we can see the fit of the correlation model above is not so good. The one on the bottom, the one considering budget is better for the analysis of our data. This confirms that the budget is indeed a very important factor that outrules most of the other ones. The importance of the other factors drops once budget is introduced. We believe that we should then continue with this factor in our establishment of the _Success score_.

<div style="text-align: center; margin: 0 auto;">
  <iframe src="assets/plots/corr_box_with_budget_color.html" width="900" height="600" frameborder="0" style="display: block; margin: 0 auto;"></iframe>
</div>


