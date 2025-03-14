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
then filtered for all data that 

Here's our cleaned data:

## Setup

Some fun facts about the setup of this project include:

* Built for [Jekyll](https://jekyllrb.com)
* Developed on GitHub and hosted for free on [GitHub Pages](https://pages.github.com)
* Coded with [Atom](https://atom.io)

Have questions or suggestions? Feel free to [open an issue on GitHub](https://github.com/poole/issues/new) or [ask me on Twitter](https://twitter.com/mdo).

Thanks for reading!
