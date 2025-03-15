---
layout: post
title: Background
---

What is Leauge of Legends?

Leauge of Legends is a 5v5 MOBA game, where a team strives to break the enemies nexus to win. Each person has
a role that they need to efficiently fufill, such as tanks, damage dealers, and supports. We will be focusing
mostly on tanks and supports for our data.

Our hypothesis question is: Do tanks/bruiser have higher damage mitigated per minute compared to tanky supports?

Why does this matter?

To a person who doesn't play games, it won't matter much. But to a person who plays leauge of legends, by understanding
how impactfull a tank/bruiser is compared to a tanky support, may help in creating a strategic team full of optimal
champions that may be better than the current optimal team.


Here's our dataframe with the 104005 rows and columns needed:

```py
df[['class_actual','damagemitigatedperminute','wardsplaced','dpm']]
```

<iframe src="{{ site.url }}{{ site.baseurl }}/assets/filtered.html" width=800 height=400 frameBorder=0></iframe>


* class_actual: A manually mapped class that dictates whether it's tank/bruiser or tanky support
* damagemitigatedperminute: Damage mitigated per minute (Damage shielded or blocked)
* wardsplaced: How many wards are placed (item in game)
* dpm: damage per minute