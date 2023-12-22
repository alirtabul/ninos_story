---
layout: conclusion
---

All along this analysis journey, we observed data, trying to make sense of them to answer our question : "Has the cast diversity an impact on the movie success" ? 
By first looking at the diversity representation on movie, we notice that the distribution isn't equal among ethnic group or gender. Over all time, `White` men tend to be more represented on movie and play more often main role than other role, espacially the `Black, Carabian` ones which are the less represented group. However, let's also notice the difference of represention between `White` and `Asian, Middle East` character isn't too important.

We also tried to determine what were the movie features that seems to impact the movie success, quantified by the `Box office revenue` and the `Success` score.
.... I want to have all the graph selected before writing too much info
To assess more precisely the correlation between the movie characteristic and the movie revenue, we used a logistic (or linear) regression to obtain correlation coefficients values. Among the most impactful factors, we found the `Budget`, the `Movie runtime` and `English language`, so technical movie aspect were important. The genre of the movie was also impactful, positively (`Adventure`,`Comdey`,...) but also negatively (`Indie`,`World cinema`). On the other hand the diversity features, such as `Diversity ethnic score` and `Gender ethnic score` had very small coefficient values, indicating a really small impact.

Finally, we se up machine learning models to predict the `Box office revenue` based on movie features.  --> Same conclusion as above

In conclusion, after analyzing our dataset, we found that for the given range of time, the diversity of the cast doesn't seem to be the most impactful factor determining the movie success. Its role seems negligeable compared to other characterstic, such as the language, the budget or the movie genre. 
Nevertheless, let's precise that isn't not because diveriyt wasn't probably impactfull on the given movies that it's an unimportant factor, a factor that shouldn't be considered. The dataset is hasn't any movie newer than 2013 and the question of diversiyt became more and more important these recent years. This consideration has probably more impact than before. Plus, the diverstity of a cast could have other impact than the `Box office revenue` only. A completly undiversted cast could have deeper and more subpile impacts than the movie revnue.....
