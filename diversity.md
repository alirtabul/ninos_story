---
layout: diversity
---

# Grouping Ethnicities into Ethnic Groups
As we mentioned earlier, the world is diverse. In fact, our dataset presents a total of 431 different ethnicities. Can you imagine? This is more than twice the number of countries in the world, we can’t work with such a large number of classes. Indeed some ethnicities might be composed of only a small number of people whereas others might be composed of thousands of people, this is not balanced at all! As such, grouping them into larger ethnic groups is a good idea. Not only does it guarantee a certain level of anonymity between ethnicities, but it also significantly balances the disparities between them.


The ethnicities were manually grouped according to the [UK's list of ethnic groups](https://www.ethnicity-facts-figures.service.gov.uk/style-guide/ethnic-groups/). All 431 ethnicities were mapped to the following 4 ethnic groups:
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

As we can see the diversity in the cinema industry can be decomposed into three timestamps:

- **1935 to 1971:**  We can see that the group Asian, Middle east and Tribes gained a lot of importance in the cinema industry. In 1935, 22% of the roles were played by actors from this group, in 1971 it was 31%! Which is quite an improvement.
- **1971 to 2008:**  We can see that the proportions are stable and do not vary that much. The number of actors continues increasing over time.
- **From 2008:** The total number of actors decreases since this point as the dataset is missing updated informations about these years. 

We can also separate men and women:

<div style="text-align: center; margin: 0 auto;">
  <!-- Replace the following line with your actual graph code -->
  <iframe src="assets/plots/actor_diversity_over_time_gender.html" width="900" height="600" frameborder="0" style="display: block; margin: 0 auto;"></iframe>
</div>

Here we can see three major trends:
- Firstly, and this is not surprising, there are many more roles that are played by men than women, indeed in 2007 the number of roles played by men was twice the number of roles played by women!
- Secondly, even with this difference we can see that the proportion of ethnicities in the two distribution is roughly the same. This is important for our later observations as, even if the men “dominates” the industry, they do not impose their “ethnic” distribution to the overall ethnic distribution.
- Lastly, we can observe that over time (expcet after 2009) the number of role played by both sex exploded. In fact we can even say that the trend of number of role payed by year is exponential. This is only based on the observations returned by the graph, hence it might be possible that this trend is no more valid after 2015. Several factors may be responsible for this increase, such as the democratization of the Internet, globalization and the explosive demand for entertainment.

## Actor diversity between movie genres
Now let’s focus on the actor diversity among movie genres.

<div style="text-align: center; margin: 0 auto;">
  <!-- Replace the following line with your actual graph code -->
  <iframe src="assets/plots/genre_diversity.html" width="900" height="600" frameborder="0" style="display: block; margin: 0 auto;"></iframe>
</div>

The first thing we can notice is the fact that the cinema industry, all time combined, is dominated by four genres: _Drama_, _Comedy_, _Romance Film_ and _Action_. Also we can observe that among those four genres, the distribution of ethnic group is roughly the same, the two dominant groups are White and Asian, Middle east and Tribes, with the group white being slightly bigger than the group Asian, Middle east and Tribes (except for the Romance movies where the two are of same importance).
Moreover those two represente more than ⅔ of the distribution in all four genres. 
But when looking at all the genres, _World cinema_ and the _Musical_ have unique distributions. Indeed, the two genres are dominated by the group _Asian Middle east and tribes_. This makes sense for _World cinema_ as it is defined as produced outside of USA.


## Actor diversity in the movies' main characters
Now, and this is the last exploration plots, we promise, let’s see the actors diversity among main and side characters.   

<div style="text-align: center; margin: 0 auto;">
  <!-- Replace the following line with your actual graph code -->
  <iframe src="assets/plots/main_roles_diversity.html" width="1100" height="600" frameborder="0" style="display: block; margin: 0 auto;"></iframe>
</div>

<div style="text-align: center; margin: 0 auto;">
  <!-- Replace the following line with your actual graph code -->
  <iframe src="assets/plots/side_roles_diversity.html" width="1100" height="600" frameborder="0" style="display: block; margin: 0 auto;"></iframe>
</div>

 Let's first analyze the barplots representing the distribution of ethnic groups playing main and side roles. As we can see, there are much more people playing side roles than main roles. This first observation is to be expected because in a movie, for a handful of main characters there are many more side characters. 
Then we can observe that, in both barplots, the *ranking* of the ethnic groups based on the number of actors are the same. However we can see that those proportions vary between main roles and side roles. Indeed for main roles the difference in number of actors from an ethnic group to another seems to be constant (~3000), whereas for side roles the difference is not constant anymore. In fact for the side roles, the ethnic group _Asia, Middle East and Tribes_ is almost as important as the ethnic group _White_ and those two categories dominate the distribution. Similarly, _Mixed or mulpiple ethnic group_ and _Black, Caribbean or African_ have a similar number of side actors, even if they represent a smaller part of the barplot.

The same observations can be done with the two piecharts.





