---
layout: analysis
---

# Correlation Analysis
## Concept
Let us now take look at the correlations between the box office revenue of the movies and other factors.

### Number of ethnic groups present in the movie
First, since our analysis is about diversity, we will look at the influence of the number of ethnic groups present. Does it appear beneficial to have multiple ethnic groups?

![Movie revenue depending on the number of ethnic groups](/assets/img/movie_revenue_per_num_groups.png)

Looking at this graph, and by our analyses, we can see that the more ethnic groups are present the higher the box office revenue! We see that there is a positive correlation between the two.

<div style="text-align: center; margin: 0 auto;">
  <iframe src="assets/plots/movies_pergroup_over_time.html" width="900" height="600" frameborder="0" style="display: block; margin: 0 auto;"></iframe>
</div>

<div style="text-align: center; margin: 0 auto;">
  <iframe src="assets/plots/box_office_over_time.html" width="900" height="600" frameborder="0" style="display: block; margin: 0 auto;"></iframe>
</div>

<div style="text-align: center; margin: 0 auto;">
  <iframe src="assets/plots/revenue_per_ethnicity.html" width="900" height="600" frameborder="0" style="display: block; margin: 0 auto;"></iframe>
</div>

### Diversity Scores
You will think, is the number of ethnic groups really what matters in diversity? What if there are is just one actor for diversity points? Well fear not! We had the same thoughts and we came up with what we call diversity scores! 

#### Ethnic Diversity Score
We penalise any over- or underrepresentation of ethnic groups in our calculations. Best score is 1 and worst score is 0. Now, let's see the relations between this score and the box office revenues.

<div style="text-align: center; margin: 0 auto;">
  <iframe src="assets/plots/ethnic_diversity_score_over_time.html" width="900" height="600" frameborder="0" style="display: block; margin: 0 auto;"></iframe>
</div>

![Movie revenue depending on the ethnic score](/assets/img/box_office_per_ethnic_score.png)


#### Gender Diversity Score
We said scores, so here is our second score. We concenrate on the gender of the actors here and we penalise any under- or overrepresentation of gender similarly to our ethnic diversity score above. 

<div style="text-align: center; margin: 0 auto;">
  <iframe src="assets/plots/gender_diversity_score_over_time.html" width="900" height="600" frameborder="0" style="display: block; margin: 0 auto;"></iframe>
</div>

<div style="text-align: center; margin: 0 auto;">
  <iframe src="assets/plots/box_office_per_gender.html" width="900" height="600" frameborder="0" style="display: block; margin: 0 auto;"></iframe>
</div>

### Genre

<div style="text-align: center; margin: 0 auto;">
  <iframe src="assets/plots/revenue_vs_genre.html" width="900" height="600" frameborder="0" style="display: block; margin: 0 auto;"></iframe>
</div>

## Correlation tables

<div style="text-align: center; margin: 0 auto;">
  <iframe src="assets/plots/corr_no_budget.html" width="900" height="600" frameborder="0" style="display: block; margin: 0 auto;"></iframe>
</div>

<div style="text-align: center; margin: 0 auto;">
  <iframe src="assets/plots/corr_revenue_with_budget.html" width="900" height="600" frameborder="0" style="display: block; margin: 0 auto;"></iframe>
</div>

3. Edit the `_config.yml` file in your forked repository to change the site title (after `title:`) and description (after `description:`).
4. Build your own page by editing this `README.md` (home page) and creating new `.md` files (other pages), formatting is done with standard [GitHub Markdown syntax](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax), we provide an example file `example.md` in the repository.
**Important**: Please include ```--- layout: default ---``` (the first three line in `example.md`) at the beginning of your every newly created `.md` file.
5. Add your new `.md` files to the site by editing the `_config.yml` file in your forked repository. Under `navigation:` add a new pair of `- title:` and `url:`, and fill their value with your page name and `.md` file name. Remember to remove the `- title:` and `url:` pair for the example page.
6. Go back to "Settings" -> "Pages" to find your website link.
7. This line is a test to see if the web site is updating

Text can be **bold**, _italic_, or ~~strikethrough~~.

[Link to another page](./another-page.html).

There should be whitespace between paragraphs.

There should be whitespace between paragraphs. We recommend including a README, or a file with information about your project.

# Header 1

This is a normal paragraph following a header. GitHub is a code hosting platform for version control and collaboration. It lets you and others work together on projects from anywhere.

## Header 2

> This is a blockquote following a header.
>
> When something is important enough, you do it even if the odds are not in your favor.

### Header 3

```js
// Javascript code with syntax highlighting.
var fun = function lang(l) {
  dateformat.i18n = require('./lang/' + l)
  return true;
}
```

```ruby
# Ruby code with syntax highlighting
GitHubPages::Dependencies.gems.each do |gem, version|
  s.add_dependency(gem, "= #{version}")
end
```

#### Header 4

*   This is an unordered list following a header.
*   This is an unordered list following a header.
*   This is an unordered list following a header.

##### Header 5

1.  This is an ordered list following a header.
2.  This is an ordered list following a header.
3.  This is an ordered list following a header.

###### Header 6

| head1        | head two          | three |
|:-------------|:------------------|:------|
| ok           | good swedish fish | nice  |
| out of stock | good and plenty   | nice  |
| ok           | good `oreos`      | hmm   |
| ok           | good `zoute` drop | yumm  |

### There's a horizontal rule below this.

* * *

### Here is an unordered list:

*   Item foo
*   Item bar
*   Item baz
*   Item zip

### And an ordered list:

1.  Item one
1.  Item two
1.  Item three
1.  Item four

### And a nested list:

- level 1 item
  - level 2 item
  - level 2 item
    - level 3 item
    - level 3 item
- level 1 item
  - level 2 item
  - level 2 item
  - level 2 item
- level 1 item
  - level 2 item
  - level 2 item
- level 1 item

### Small image

![Octocat](https://github.githubassets.com/images/icons/emoji/octocat.png)

### Large image

![Branching](https://guides.github.com/activities/hello-world/branching.png)


### Definition lists can be used with HTML syntax.

<dl>
<dt>Name</dt>
<dd>Godzilla</dd>
<dt>Born</dt>
<dd>1952</dd>
<dt>Birthplace</dt>
<dd>Japan</dd>
<dt>Color</dt>
<dd>Green</dd>
</dl>

```
Long, single-line code blocks should not wrap. They should horizontally scroll if they are too long. This line should be long enough to demonstrate this.
```

```
The final element.
```

