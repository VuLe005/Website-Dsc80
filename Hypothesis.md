---
layout: page
title: Hypothesis Testing
---

<p class="message">
    This section is dedicated to the Hypothesis Testing
</p>

Question: Do tanks/bruiser have higher damage mitigated per minute compared to tanky supports?

Null Hypothesis: Tanks/bruisers have a higher damage mitigated than tanky supports.

Alternate Hypothesis: Tanks/bruisers have a lower damage mitigated than tanky supports.

Test Statistic: Difference in Means

Alpha Level: .05

Explanation:

    Null Hypothesis: Tanks/bruisers should have higher damage mitigated per minute due to being a solo laner ( Top Lane )

    Alternate Hypothesis: Opposite to the null hypothesis. Tanky supports should be protecting their ADC, and shielding the damage

    Test Statistic: We should be able to see a mean difference if true, since damage mitigated per minute is a numerical value

    Alpha Level: We set an alpha level of .05, because this is common and is enough to showcase if our p-value is true



```py
filtered_df.groupby('class_actual')['damagemitigatedperminute'].agg(['mean','count'])
```
<iframe src="{{ site.url }}{{ site.baseurl }}/assets/groupby.html" width=800 height=200 frameBorder=0></iframe>

We now need to observe the mean difference between both tank/bruiser and tanky supports. Here's
an interactable graph for damage mitgated per minute for each class

<iframe src="{{ site.url }}{{ site.baseurl }}/assets/damagemitigatedperminute_for_class.html" width=800 height=600 frameBorder=0></iframe>

In order to test our data, we need to shuffle the values around.
```py
with_shuffled = filtered_df.assign(Shuffled_Weights=np.random.permutation(filtered_df['damagemitigatedperminute']))
with_shuffled.head()
```

<iframe src="{{ site.url }}{{ site.baseurl }}/assets/shuffled_df.html" width=800 height=400 frameBorder=0></iframe>

```py
group_means = with_shuffled.groupby('class_actual').mean()
group_means
```

<iframe src="{{ site.url }}{{ site.baseurl }}/assets/group_means.html" width=800 height=200 frameBorder=0></iframe>

We can now compare the original graph, and the shuffled columns graph.
<iframe src="{{ site.url }}{{ site.baseurl }}/assets/shuffled_graph1.html" width=800 height=600 frameBorder=0></iframe>

<iframe src="{{ site.url }}{{ site.baseurl }}/assets/shuffled_graph2.html" width=800 height=600 frameBorder=0></iframe>

Using the difference in means, we have found that the observed difference is -330, and our p-value is 0.
This suggests that tanks/bruiser have a higher damage mitigated overall compared to tanky support.

```py
n = 500

differences = []
for _ in range(n):

    with_shuffled = filtered_df.assign(Shuffled_Weights=np.random.permutation(filtered_df['damagemitigatedperminute']))

    group_means = (
        with_shuffled
        .groupby('class_actual')
        .mean()
        .loc[:, 'Shuffled_Weights']
    )
    difference = group_means.loc['tanky support'] - group_means.loc['tank/bruiser']

    differences.append(difference)
    
mean_weights = filtered_df.groupby('class_actual')['damagemitigatedperminute'].mean()
observed_difference = mean_weights['tanky support'] - mean_weights['tank/bruiser']
print(observed_difference)

p_value = (np.array(differences) <= observed_difference).mean()
print(p_value)
```

```py
-330.57659934042726
0.0
```

Conclusion:
    P-value = 0.0
    Since our P-value (0.0) is less than our significance level (alpha = .05), this suggests that tanks/bruiser
    have a higher damage mitigated per minute than tanky supports.
