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
Using three statististical test and visualization, we can check if these two groups are different or not.

```python
# T-test
t_stat, t_p = stats.ttest_ind(group1, group2)

# Wilcoxon rank-sum test (also known as Mann-Whitney U test)
wilcox_stat, wilcox_p = stats.mannwhitneyu(group1, group2)

# Kolmogorov-Smirnov test
ks_stat, ks_p = stats.ks_2samp(group1, group2)

print(f"T-test p-value: {t_p}")
print(f"Wilcoxon rank-sum test p-value: {wilcox_p}")
print(f"Kolmogorov-Smirnov test p-value: {ks_p}")

# T-test
t_stat, t_p = stats.ttest_ind(group1, group2)

# Wilcoxon rank-sum test (also known as Mann-Whitney U test)
wilcox_stat, wilcox_p = stats.mannwhitneyu(group1, group2)

# Kolmogorov-Smirnov test
ks_stat, ks_p = stats.ks_2samp(group1, group2)

print(f"T-test p-value: {t_p}")
print(f"Wilcoxon rank-sum test p-value: {wilcox_p}")
print(f"Kolmogorov-Smirnov test p-value: {ks_p}")


import matplotlib.pyplot as plt
import seaborn as sns
from scipy import stats

# Create a figure with 3 subplots in the same row
fig, axes = plt.subplots(1, 3, figsize=(18, 6))

# Create scatter plot
sns.swarmplot(x='group', y='response', data=groups_long, palette='Accent', ax=axes[0])
axes[0].set_title('Scatter Plot')

# Perform and annotate Kolmogorov-Smirnov test
ks_stat, ks_pval = stats.ks_2samp(group1, group2)
axes[0].annotate(f'Kolmogorov-Smirnov p-value: {ks_pval:.2f}', xy=(0.05, 0.95), xycoords='axes fraction')

# Create box plot
sns.boxplot(x='group', y='response', data=groups_long, palette='Accent', ax=axes[1])
axes[1].set_title('Box Plot')

# Perform and annotate Wilcoxon rank-sum test
wilcoxon_stat, wilcoxon_pval = stats.ranksums(group1, group2)
axes[1].annotate(f'Wilcoxon rank-sum p-value: {wilcoxon_pval:.2f}', xy=(0.05, 0.95), xycoords='axes fraction')

# Create bar plot
sns.barplot(x='group', y='response', data=groups_long, palette='Accent', ax=axes[2])
axes[2].set_title('Bar Plot')

# Perform and annotate t-test
t_stat, t_pval = stats.ttest_ind(group1, group2)
axes[2].annotate(f't-test p-value: {t_pval:.2f}', xy=(0.05, 0.95), xycoords='axes fraction')

# Show the plot
plt.tight_layout()

# Save the figure as a PDF in the 'Figures' folder
plt.savefig('Figures/mean_seperation.pdf', format='pdf')
```
<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/figures/mean_seperation.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
