---
layout: post
title: Friends Don't Let Friends 
date: 2024-05-28 15:09:00
description: an example of a blog post with some code
tags: formatting code
categories: Data Viz
featured: true
---

This is a series motivated by the popular friends don't let friends in R.
My goal is to rewrite the codes in python and explore the common visualization mistakes in python ecosystem.

Let's have fun:
It is possible to have two groups with similar means but different distribution, be cautious about the type of visualisation you use when representing data.
Alwaya double check.

````markdown
```python
import numpy as np
import pandas as pd
from scipy import stats
from scipy.stats import iqr
import random


random.seed(123)
# Normal distribution
group1 = np.random.normal(loc=1, scale=1, size=100)

# Log-normal distribution
meanlog = np.log(1**2/np.sqrt(1**2 + 1**2))
sdlog = np.sqrt(np.log(1+(1**2/1**2)))
group2 = np.random.lognormal(mean=meanlog, sigma=sdlog, size=100)


df = pd.DataFrame({
    'group1': group1,
    'group2': group2
})
groups_long = df.melt(var_name='group', value_name='response')
```
````
