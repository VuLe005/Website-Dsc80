---
layout: page
title: Hypothesis Testing
---

Question: Do tanks/bruiser have higher damage mitigated per minute compared to tanky supports?

<p class="message">
    This section is dedicated to the Hypothesis Testing
</p>

```py
filtered_df.groupby('class_actual')['damagemitigatedperminute'].agg(['mean','count'])
```

We now need to observe the mean difference between both tank/bruiser and tanky supports. Here's
an interactable graph that 

<iframe src="{{ site.url }}{{ site.baseurl }}/assets/groupby.html" width=800 height=600 frameBorder=0></iframe>

<iframe src="{{ site.url }}{{ site.baseurl }}/assets/shuffled_df.html" width=800 height=600 frameBorder=0></iframe>

<iframe src="{{ site.url }}{{ site.baseurl }}/assets/group_means.html" width=800 height=600 frameBorder=0></iframe>

<iframe src="{{ site.url }}{{ site.baseurl }}/assets/shuffled_graph1.html" width=800 height=600 frameBorder=0></iframe>

<iframe src="{{ site.url }}{{ site.baseurl }}/assets/shuffled_graph2.html" width=800 height=600 frameBorder=0></iframe>

## Setup

Some fun facts about the setup of this project include:

* Built for [Jekyll](https://jekyllrb.com)
* Developed on GitHub and hosted for free on [GitHub Pages](https://pages.github.com)
* Coded with [Atom](https://atom.io)

Have questions or suggestions? Feel free to [open an issue on GitHub](https://github.com/poole/issues/new) or [ask me on Twitter](https://twitter.com/mdo).

Thanks for reading!
