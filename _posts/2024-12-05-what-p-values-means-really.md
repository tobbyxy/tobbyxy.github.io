---
layout: post
title: What a p value really means?
date: 2024-12-05 20:01:00
description: 
tags: stats maths
categories: post
thumbnail: 
---
what a pvalue really means?

Correct understanding of p value is not trivial, and the interpretation of p values
is mostly misunderstood. I find myself having to go back to terminologies and basics to 
properly interprete statistically significant findings.

Terminologies first-

sample: an experiment or data we collect to say something about a population. it is usually
used to make inference(conclusion) about a population. ideally should be a good representation of the population
population: The set of all possible data we can collect for a given observation (e.g height)
statistics: measures calculated from the sample, used to estimate population parameters
Test statistics: value calculated from the sample data that is compared to the critical value to determine whether to reject the null hypothesis. 
Null Hypothesis: A statement asserting that there is no (effect, difference, relationship) in the variables being studied. e.g "there is no differece in average height between two groups"
Critical region: is the region or range of values which we preset that leads to rejection of the null hypothesis
alpha: significance level, is the probability of rejecting the null hypothesis when it is true (Type I error)

Example Next-
boys are known to have a mean weight of 85 pounds. There is a complaint about boys living in iowa to be underfed.
Data is collected for evidence, n = 25 (of the same age) are weighed and found to have a mean weight of 80.94 pounds.
It is known that the population standard deviation is 11.6 pounds.

In this example we can calculate the Z statistics, and use it to test our null hypothesis.

z = -1.75

```r
library(ggplot2)

# Set parameters
mu0 <- 0  # Null hypothesis mean
sigma <- 1  # Standard deviation
alpha <- 0.05  # Significance level
z_stat <- -1.75  # Observed z-statistic

# Calculate critical values and p-value
z_crit <- qnorm(alpha/2, lower.tail = FALSE)
p_value <- pnorm(z_stat, lower.tail = TRUE)

# Create data for plotting
x <- seq(-4, 4, length.out = 1000)
y <- dnorm(x)
df <- data.frame(x = x, y = y)

# Create the plot
ggplot(df, aes(x = x, y = y)) +
  geom_line() +
  geom_area(data = subset(df, x <= -z_crit | x >= z_crit), fill = "red", alpha = 0.3) +
  geom_vline(xintercept = c(-z_crit, z_crit), linetype = "dashed", color = "red") +
  geom_vline(xintercept = z_stat, linetype = "solid", color = "blue") +
  annotate("text", x = -z_crit - 0.5, y = 0.2, label = "Critical\nRegion", color = "red") +
  annotate("text", x = z_crit + 0.5, y = 0.2, label = "Critical\nRegion", color = "red") +
  annotate("text", x = z_stat, y = 0.3, label = paste("z =", round(z_stat, 2)), color = "blue") +
  annotate("text", x = -3, y = 0.3, label = paste("p-value =", round(p_value, 4)), color = "blue") +
  labs(title = "Standard Normal Distribution with Critical Regions",
       x = "Z-score", y = "Density") +
  theme_minimal()
```
The critical region to reject the null hypothesis at the alpha level 0.05 if z < -1.645. Therefore we reject the Null
hypothesis. using the critical region approach. 
We can also calculate the probability of seeing a new test statistics as extreme( or more extreme)as our observed test statistics, if
the null hypothesis was true. p(z < -1.75), which is equal to 0.0401.This probability is called the P-value. 

It is the probability that depends on the distribution of the test statistics.it tells us whether or not (there is an effect/difference/relationship).
It is not the probability of the null hypothesis being true nor does it say anything about size (how large or small) the effect will be.

P-value is the smallest alpha value that will cause us to reject the null hypothesis. if the p value is less than alpha, we reject the null hypothesis
and if greater than alpha, we fail to reject the hypothesis.

While this example is trivial, care must be taken when interpreting P-values. A result can be statistically significant without having any real world
implication (practical signficance). A good domain knowledge is necessary to assert the practicality of statistically significant results, other
potential forms of error (selection, measurement) must be considered.

A large sample size and low variability in the data can also produce very low p values whose effect size is negligible. while small sample size might 
fail to detect meaningful effects(Type II error). Achieving statistical significance does not eliminate all forms of bias in a study.

In conclusion, we should be careful of wrongful interpretation of research findings by merely overemphasing on low P-values, which might lead to 
misleading conclusion and oversimlification of complex research.
