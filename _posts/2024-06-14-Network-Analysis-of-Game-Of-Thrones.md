---
layout: post
title: A Network Analysis of Game of Thrones
date: 2024-05-29 08:57:00-0400
description: Data Camp Fun Project
tags:  jupyter Datacamp
categories: fun project
related_posts: false
---

Network analysis, graphs, page rank, evolution are all interesting concepts I explore in this fun project.
Networks evolve as seen in game of thrones characters, Important nodes become less important as we go further in books.

1. Winter is Coming. 
If you haven't heard of Game of Thrones, then you must be really good at hiding.
Game of Thrones is the hugely popular television series by HBO based on the (also)
hugely popular book series A Song of Ice and Fire by George R.R. Martin. In this notebook,
we will analyze the co-occurrence network of the characters in the Game of Thrones books.
Here, two characters are considered to co-occur if their names appear in the vicinity of 15 words from one another in the books.

{::nomarkdown}
{% assign jupyter_path = "assets/jupyter/Network-Analysis-of-game-of-thrones.ipynb" | relative_url %}
{% capture notebook_exists %}{% file_exists assets/jupyter/Network-Analysis-of-game-of-thrones.ipynb %}{% endcapture %}
{% if notebook_exists == "true" %}
{% jupyter_notebook jupyter_path %}
{% else %}

<p>Sorry, the notebook you are looking for does not exist.</p>
{% endif %}
{:/nomarkdown}
