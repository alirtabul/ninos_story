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
  <iframe src="assets/plots/actor_diversity_over_time.html" width="1200" height="700" frameborder="0" style="display: block; margin: 0 auto;"></iframe>
</div>
From this plot we can deduce the following points:

- There was a significant explosion in actors from approximately 1984 onwards. 
- Between 1940-1950, movies were dominantly played by people in the 'White' ethnic group.
- From 1950 onwards, the number of ethnic groups were more balanced. In particular, the dominant ethnic groups are 'Asian, Middle East and Tribes' and 'White'.
- There is a decrease in actors from 2008 onwards which was probably due to the global economic crisis at the time.



