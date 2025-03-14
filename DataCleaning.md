---
layout: page
title: Data Cleaning and EDA
---

Question: Do tanks/bruiser have higher damage mitigated per minute compared to tanky supports?

<p class="message">
  This section is dedicated to describing how we cleaned and pre-processed the data.
</p>


Here's our initial data:

```py
print(raw.head())
```

<iframe src="{{ site.url }}{{ site.baseurl }}/assets/raw_head.html" width=800 height=600 frameBorder=0></iframe>

This data has too many unnecessary columns that aren't needed such as first dragon, first baron, golddiffat20
which won't answer our question. Thus, we dropped the majority of the columns. After dropping columns, we 
filtered out the incomplete data using the "completness" column, and then dropped all NA.

Here's our cleaned data:

```py
print(cleaned_df.head())
```

<iframe src="{{ site.url }}{{ site.baseurl }}/assets/cleaned_df_head.html" width=800 height=600 frameBorder=0></iframe>



We then created a new column, "class" and "class_actual", which shows whether or not a champion is a 
tank/bruiser or a tanku support. To determine the class, we filtered for champions with high damage
mitigated per minute and amounts of wards placed, and compared it to "class_actual" which is a manually
mapped class to compare accuracy.

```py
accuracy = (cleaned_df['class'] == cleaned_df['class_actual']).mean()
accuracy
0.7817412624393058
```

Univariate Analysis:

<iframe src="{{ site.url }}{{ site.baseurl }}/assets/earned_gold_distribution.html" width=800 height=600 frameBorder=0></iframe>

* This bimodal curve distribution tells us that there are two distinct groups of gold-earners within this dataset
* Makes sense because certain champions and positions are expected to earn gold on different levels

Bivariate Analysis:

<iframe src="{{ site.url }}{{ site.baseurl }}/assets/damagetakenperminute.html" width=800 height=600 frameBorder=0></iframe>

* Because of the variance in stats for each position, we can have some confidence that this will be a good metric for predicting positions
* It is clear that top and jungle positions take the most damage while bottom and support take the least

Assesment of missingness:

One column that depends on another is towers and gamelength, which the longer the game happens,
the more towers are destroyed:

<iframe src="{{ site.url }}{{ site.baseurl }}/assets/towers.html" width=800 height=600 frameBorder=0></iframe>

One columns that does not depend on another is towers and barons, as they are unrelated in missingness:

<iframe src="{{ site.url }}{{ site.baseurl }}/assets/barons.html" width=800 height=600 frameBorder=0></iframe>
