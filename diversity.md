---
layout: diversity
---

# Grouping Ethnicities into Ethnic Groups
As we mentioned earlier, the world is diverse. In fact, our dataset presents a total of 431 different ethnicities. Can you imagine ? This is more than twice the number of countries in the world, we can’t work with such a large number of classes. Indeed some ethnicities might be composed of only a small number of people whereas others might be composed of thousands of people, this is not balanced at all ! As such, grouping them into larger ethnic groups is a good idea. Not only does it guarantee a certain level of anonymity between ethnicities, but it also significantly balances the disparities between them.


As such, the ethnicities were manually grouped according to the [UK's list of ethnic groups](https://www.ethnicity-facts-figures.service.gov.uk/style-guide/ethnic-groups/). All 431 ethnicities were mapped to the following 4 ethnic groups:
- White
- Black, Caribbean or African
- Asian, Middle East and Tribes
- Mixed or multiple ethnic groups

By looking at the proportion of ethnic groups below, we can see that the ethnic groups “White” and “Asian, Middle East and Tribes” account for roughly two thirds of the population:
<div style="text-align: center; margin: 0 auto;">
  <!-- Replace the following line with your actual graph code -->
  <iframe src="assets/plots/ethnic_group_counts.html" width="700" height="700" frameborder="0" style="display: block; margin: 0 auto;"></iframe>
</div>

# Looking at the data
Before diving into any kind of analysis, let’s have a look at our data so that we have a feeling of its content. 

## Actor diversity over time
Over the past century many things have changed, trends and fashion are not anymore the same, trade and technology have massively accelerated leading today to a more diverse world than ever. Let’s see if this diversity increase is present in the cinema industry.

<div style="text-align: center; margin: 0 auto;">
  <!-- Replace the following line with your actual graph code -->
  <iframe src="assets/plots/actor_diversity_over_time.html" width="900" height="600" frameborder="0" style="display: block; margin: 0 auto;"></iframe>
</div>

As we can see the diversity in the cinema industry can be decomposed into three timestamps

- 1935 to 1971:  We can see that the group Asian, Middle east and Tribes gained a lot of importance in the cinema industry. In 1935, 22% of the roles were played by actors from this group, in 1971 it was 31% ! Which is quite an improvement.
- 1971 to 2011:  We can see that the proportions are stable and do not vary that much.
- From 2011: We can see that a lot of changes occurred, especially for the group Mixed or multiple ethnic groups. This is because the presence of metices has exploded in the cinema industry and minorities are better represented nowadays. Also if it was possible to see until now, the changes should have been even more pronounced. 

We can also separate men and women:

<div style="text-align: center; margin: 0 auto;">
  <!-- Replace the following line with your actual graph code -->
  <iframe src="assets/plots/actor_diversity_over_time_gender.html" width="900" height="600" frameborder="0" style="display: block; margin: 0 auto;"></iframe>
</div>

Here we can see three major trends:
- Firstly, and this is not surprising, there are many more roles that are played by men than women, indeed in 2007 the number of roles played by men was twice the number of roles played by women !
- Secondly even with this difference we can see that the proportion of ethnicities in the two distribution is roughly the same. This is important for our later observations as, even if the men “dominates” the industry, they do not impose their “ethnic” distribution to the overall ethnic distribution as the women have the same distribution.
- Lastly we can observe that in 1990 the number of role played by both sex exploded, in fact we can even say that the trend of number of role payed by year is exponential. This is only based on the observations returned by the graph, hence it might be possible that this trend is no more valid after 2015. In any case we can still observe an explosion around 1990. Several factors may be responsible for this, such as the democratization of the Internet, globalization and the explosive demand for entertainment.

## Actor diversity between movie genres
Now let’s focus on the actor diversity among movie genres.

<div style="text-align: center; margin: 0 auto;">
  <!-- Replace the following line with your actual graph code -->
  <iframe src="assets/plots/genre_diversity.html" width="900" height="600" frameborder="0" style="display: block; margin: 0 auto;"></iframe>
</div>

The first thing we can notice is the fact that the cinema industry, all time combined, is dominated by four genres: Draman, Comedy, Romance Film and Action. Also we can observe that among those four genres, the distribution of ethnic group is roughly the same, the two dominant groups are White and Asian, Middle east and Tribes and when combined, with the group white being slightly bigger than the group Asian, Middle east and Tribes (except for the Romance movies where the two are of same importance). Moreover those two represente more than ⅔ of the distribution in all four genres. 
But now if we interest into the rest of the genres we can see some that are really different than the other regarding only the distribution on ethnic group. Indeed two genres are dominated by the group Asian Middle east and tribes, the genre World cinema and the genre Musical. This shows that in general movie genre behaves similarly in terms of ethnic distribution, which is similar to our previous observation with men and women, but some of them are really different from the “norm” such as the genres world cinema and Musical. 

## Actor diversity in the movies’ main characters
Now, and this is the last exploration plots we promise, let’s see the actors diversity among main/side characters.

<div style="text-align: center; margin: 0 auto;">
  <!-- Replace the following line with your actual graph code -->
  <iframe src="assets/plots/main_roles_diversity.html" width="900" height="600" frameborder="0" style="display: block; margin: 0 auto;"></iframe>
</div>

Before analyzing the piecharts let's analyze the barplots representing the distribution of ethnic groups playing main/side roles. As we can see there are much more people playing side roles than main roles, this first observation is to be expected because in a movie, for 3-5 main characters there are much more side characters. Then we can observe that, in both barplots, the *ranking* of the most important ethnic group based on the number of actor are the same. However we can see that those proportions vary between main roles and side roles. Indeed for main roles the difference in number of actors from an ethnic group to another seems to be constant ($\approx 3000$), whereas for side roles we can see that this difference is no more constant. In fact the ethnic group ``Asia, Middle East and Tribes`` is almost as important as the ethnic group ``White`` and those two categories dominate the distribution. Similarly, ``Mixed or mulpiple ethnic group`` and ``Black, Caribbean or African`` have a similar number of side actors, even if they represent a smaller part of the barplot.

The same observations can be done with the two piecharts.





