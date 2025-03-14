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





## Setup

Some fun facts about the setup of this project include:

* Built for [Jekyll](https://jekyllrb.com)
* Developed on GitHub and hosted for free on [GitHub Pages](https://pages.github.com)
* Coded with [Atom](https://atom.io)

Have questions or suggestions? Feel free to [open an issue on GitHub](https://github.com/poole/issues/new) or [ask me on Twitter](https://twitter.com/mdo).

Thanks for reading!
