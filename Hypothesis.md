---
layout: page
title: Hypothesis Testing
---

<p class="message">
    This section is dedicated to the Hypothesis Testing
</p>

```py
filtered_df.groupby('class_actual')['damagemitigatedperminute'].agg(['mean','count'])
```

<iframe src="{{ site.url }}{{ site.baseurl }}/assets/groupby.html" width=800 height=600 frameBorder=0></iframe>

<iframe src="{{ site.url }}{{ site.baseurl }}/assets/damagemitigatedperminute_for_class.html" width=800 height=600 frameBorder=0></iframe>

<iframe src="{{ site.url }}{{ site.baseurl }}/assets/damagetakenperminute.html" width=800 height=600 frameBorder=0></iframe>


## Setup

Some fun facts about the setup of this project include:

* Built for [Jekyll](https://jekyllrb.com)
* Developed on GitHub and hosted for free on [GitHub Pages](https://pages.github.com)
* Coded with [Atom](https://atom.io)

Have questions or suggestions? Feel free to [open an issue on GitHub](https://github.com/poole/issues/new) or [ask me on Twitter](https://twitter.com/mdo).

Thanks for reading!
