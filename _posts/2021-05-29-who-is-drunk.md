---
layout: post
title: Who is Drunk, and When in Ames, Iowa?
date: 2024-05-29 08:57:00-0400
description: Data Camp Fun Project
tags:  jupyter Datacamp
categories: fun project
related_posts: false
---

This project was of interest to me because I'm currenlty in Ames, Iowa. It allows me to also practise my data science skills on past decision made.
We are trying to answer the question: Was it a good decision to cancel the [VEISHEA](https://en.wikipedia.org/wiki/VEISHEA)

From Wikipedia: "VEISHEA was an annual week-long celebration held each spring on the campus of Iowa State University in Ames, Iowa. The celebration featured an annual parade and many open-house demonstrations of the university facilities and departments. Campus organizations exhibited products, technologies, and held fundraisers for various charity groups. In addition, VEISHEA brought speakers, lecturers, and entertainers to Iowa State. [...] VEISHEA was the largest student-run festival in the nation, bringing in tens of thousands of visitors to the campus each year."

This over 90-year tradition in Ames was terminated permanently after riots in 2014, where drunk celebrators flipped over multiple vehicles and tore light poles down. This was not the first incidence of violence and severe property damage in VEISHEA's history. Did former President Leath make the right decision by canceling VEISHEA?


{::nomarkdown}
{% assign jupyter_path = "assets/jupyter/who_is_drunk_notebook.ipynb" | relative_url %}
{% capture notebook_exists %}{% file_exists assets/jupyter/who_is_drunk_notebook.ipynb %}{% endcapture %}
{% if notebook_exists == "true" %}
{% jupyter_notebook jupyter_path %}
{% else %}

<p>Sorry, the notebook you are looking for does not exist.</p>
{% endif %}
{:/nomarkdown}

