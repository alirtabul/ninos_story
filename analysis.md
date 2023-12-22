---
layout: analysis
---

# Movie correlation Analysis
## Concept
In this part of our project, we'll try to observe if the diversity seems to impact the movie success. And if it isn't the case what are the other factor that do influence a movie outcome ? In other words, we'lllook at the correlations between the box office revenue of the movies and its characteristics, such as the year of release, the genre, the cast or the budget.

## Defining the succes of a movie 
As mentionned before, we would like assess the success of movies depending on different factors. But how do we define a movie success ? 

### Box office revenue
The first features in our dataset that could quantify a movie succes is the `Box office revenue`. Indeed it's usually true that the more successful a movie is, the more people are going to watch it in theater and the more money it's going to make.

For our analysis, we also care about the temporal evolution of movie success and its features over time. Thus for a better comprehension, let's vizualise the mean `Box office revenue` over time.

<div style="text-align: center; margin: 0 auto;">
  <iframe src="assets/plots/box_office_over_time.html" width="900" height="600" frameborder="0" style="display: block; margin: 0 auto;"></iframe>
</div>

We can see that the mean box office revenue is increasing with time. This could be due to a lot of different factors:
- First the revenue currency isn't the same 100 hundred years ago and now and revnue value entered in 1956 could be doesn't have the same impact or meaning than now
- With time, more money is given to produce movie 
Few additional comment: the inlfation also plays an role impacting the real power of this value. To have more accurate values, we should have taking in account the inflation.


### Success score 
**Should we talk about it now ?**

## Note considering dataset sizes
A note concerning our features and the dataset size. For most of our movie success analysis, we're going to use `Box office revnue` rather than the `Success` and we won't consider too much the `Vote average` and the `Budget`. To explain, the situation, these two last features come from the additional dataset Kaggle and unfortunately this dataset is smaller than the CMU one. Thus if we want to do some analysis using the `Budget` for example, we have to remove a considerabe high number of `Nan`or 0 value, reducing considerably the dataset (from 20'000 to less than 2'000). That's why we'll mosly focus our analysis on the `B`

***

## Ethnic representation analysis

### Box office revenue depending on ethnic group
We'll start answering one of the first question that we could ask. Is there a difference in the Budget depending on the ethnic group ? 
Let's have a look at this !

<div style="text-align: center; margin: 0 auto;">
  <iframe src="assets/plots/revenue_per_ethnicity.html" width="900" height="600" frameborder="0" style="display: block; margin: 0 auto;"></iframe>
</div>

We see that actors of all ethnicity play on average in similarly lucrative movies. Our statistical anlyses tell us however that white people tend to play in the movies with highest box office revenues, while Asian people tend to play in the thos with the lowest box office revenues. <br>

It could also be relevant to analyze how does the mean box office revenue evolved over time.

<div style="text-align: center; margin: 0 auto;">
  <iframe src="assets/plots/budget_ethnic_group_over_time.html" width="900" height="600" frameborder="0" style="display: block; margin: 0 auto;"></iframe>
</div>

All different ethnicities seem to follow the same general behaviour but `White` actors still seem to play in movie which ended up with a higher revenue.


### Ethnic Diversity Score
--> Maybe explain better why we need the ethnic diversity score (Because we need a variable )
We wanted a variable to quantify the diversity representation in movie. We first try to use the the mean number of unique ethicities but it does't take in account the proportion of each ethinicities in the cast. For example, if you have 20 white actors, 1 asian, 1 middle east and 1 black one, the score will be of 4 however we can really say that this cast is really diverse.


The `Ethnic diversity score` roots from the idea that all ethnicities should be of equal percentage in the cast. We have 4 ethnic groups in our analysis so each of them should make up 25% of the cast. In our calculation, we penalise the changes with respect to this 25%, we subtract the difference for each group to 1. When en ethnic group makes up the whole cast this approach would yield -1 as a score. 

We penalise any over- or underrepresentation of ethnic groups in our calculations. Best score is 1 and worst score is 0. Now, let's see the relations between this score and the _Box office revenue_.
--> Should try to merge this 2 explanations. A bit clearer than the first one but more in detailed than the second one.


We see that this score tends to get higher as we get closer to current days. This is good news for the representation of everyone on the big screen. 

<div style="text-align: center; margin: 0 auto;">
  <iframe src="assets/plots/ethnic_diversity_score_over_time.html" width="900" height="600" frameborder="0" style="display: block; margin: 0 auto;"></iframe>
</div>



## Gender representation analysis

### Box office revenue depending on the gender
As mentionned before, our analysis is mostly focus on the diversity and thus gendre representation also matter to us. Let's see the differences between men and women. In this following graph we might think that the mean box office revenue is similar for both, but we want to highlight that the scale is logarithmic! Do not rely only on your eyes! Small differences on the graph are extually exponentially bigger in real (**not so sure of that**)

<div style="text-align: center; margin: 0 auto;">
  <iframe src="assets/plots/box_office_per_gender.html" width="900" height="600" frameborder="0" style="display: block; margin: 0 auto;"></iframe>
</div>

Not only is there a 4 million dollars gap between the medians, but a quick t-test confirms that this difference is statistically significant. Hence, women play in less well-payed movies ---> We don't know if they're less paid, it just that the movie had a lower revenue. Hopefully, this might improve in the future.<br>

### Gender Diversity Score
We said scores, so here is our second score. We concenrate on the gender of the actors here and we penalise any under- or overrepresentation of gender similarly to our ethnic diversity score above. <br>

It's now time to see the evolution of this variable over time.

<div style="text-align: center; margin: 0 auto;">
  <iframe src="assets/plots/gender_diversity_score_over_time.html" width="900" height="600" frameborder="0" style="display: block; margin: 0 auto;"></iframe>
</div>

The growth on this graph is somewhat steeper than the one on the `Ethnic diversity score`. Starting with the mid to late 90s, the score has not gone below 0.5, but has also not gone much higher. Nonetheless, this seems like progress to us.

So how do movies do with respect to their `Gender diversity score`?

<div style="text-align: center; margin: 0 auto;">
  <iframe src="assets/plots/box_office_dep_ethnic_diversity_score.html" width="900" height="600" frameborder="0" style="display: block; margin: 0 auto;"></iframe>
</div>


A first glance at this graph shows that mostly low diversity scores have high box office revenues. Does that mean that when there are women in movies they bring down the revenues? No, of course not. It just means that the most popular movies until now had less women, which is not so surprising. Our `Gender diversity score` also only takes into account the presence of women, not their usefullness to the plot, but this is getting out of the scope of our research. If you are intereset in this topic we invite you to look up the <a href="https://en.wikipedia.org/wiki/Bechdel_test">Bechdel test</a>. ---> Be carefull a low value of diversity gendre score doesn't mean that there are a lot of women, but that there is a unbalanced gender cast. A movie with only women would have a low score as well.


### Genre

We can also think about the genre of the movie we are talking about. Depending on the genre, people will be more or less likely to go to the cinema and so to contribute to the _Box office revenue_. We show here the **Top 10** most represented movie genres.

<div style="text-align: center; margin: 0 auto;">
  <iframe src="assets/plots/revenue_vs_genre.html" width="900" height="600" frameborder="0" style="display: block; margin: 0 auto;"></iframe>
</div>

We notice that Adventure movies are the most lucrative, along with Thrillers, while Indie and World Cinema movies are on the lowest sides. Indie movies tend less to be in cinema than other types of movies and World Cinema is usually less globalised. Thus, not many surprised here.



## Correlation tables
We would like to use machine learning tools to see if we can predict the `Box office revenue` value of a movie based on its characteristics, such as diversity, budget or genres. 

We divide this part in two, wanting to investigate if we could predict a success score without taking into account the budget of the movie. --> **Ok true but the main reason why we divided the analysis in two was to be careful with the dataset set size reduction when using the Budget. Not using the Budget at the begining allow us to do an estimation on a big datset while we used the Budget, we get a importat feature but the downside is that the dataset is super small and then it's hard to generalize. I think it's important to mention that**

<div style="text-align: center; margin: 0 auto;">
  <iframe src="assets/plots/corr_box_no_budget_color.html" width="900" height="600" frameborder="0" style="display: block; margin: 0 auto;"></iframe>
</div>

As we can see the fit of the correlation model above is not so good. --> **Why ? Explain why (R^2 value).** The one on the bottom, which considers budget is better for the analysis of our data. This confirms that the budget is indeed a very important factor that outrules most of the other ones --> **Again the datset is super small, we should be careful about these sentences**. The importance of the other factors drops once budget is introduced. We believe that we should then continue with this factor in our establishment of the _Success score_.

<div style="text-align: center; margin: 0 auto;">
  <iframe src="assets/plots/corr_box_with_budget_color.html" width="900" height="600" frameborder="0" style="display: block; margin: 0 auto;"></iframe>
</div>

We notice that in both figures, the features related to the diverstiy (`Ethnic diversity score` and `Gender diversity score`) have a correlation coefficient really close to 0, meaning that theit impact on the `Box office revenue` is really small and almost negligeable (especially for the situation where we take the budget into acccount).
One more time, it seems that the diversity has negligeable impact on the `Box office revenue`.







-------#######---------
------ Old version -------
### Number of ethnic groups present in the movie  ----> I don't think it's relevant to talk about the number of ethnic group. It's better to just use the ethnic diversity score
First, since our analysis is about diversity, we will look at the influence of the number of ethnic groups present. Does it appear beneficial to have multiple ethnic groups?

![Movie revenue depending on the number of ethnic groups](/assets/img/movie_revenue_per_num_groups.png)

Looking at this graph, and by our analyses, we can see that the more ethnic groups are present the higher the box office revenue! We see that there is a positive correlation between the two. However, we also notice that the uncertainty of the income also becomes greater.

<div style="text-align: center; margin: 0 auto;">
  <iframe src="assets/plots/movies_pergroup_over_time.html" width="900" height="600" frameborder="0" style="display: block; margin: 0 auto;"></iframe>
</div>

Over the years, more and more movies are produced (and introduced in our data set), so more diverse movie are made. We notice, nonetheless, that movies with all four ethnic groups present are the rarest. 

<div style="text-align: center; margin: 0 auto;">
  <iframe src="assets/plots/box_office_over_time.html" width="900" height="600" frameborder="0" style="display: block; margin: 0 auto;"></iframe>
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


