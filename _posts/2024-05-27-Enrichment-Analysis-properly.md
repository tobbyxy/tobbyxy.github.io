---
layout: post
title: Are you doing Enrichment Analysis Properly?
date: 2024-05-27 21:01:00
description: 
tags: Methods
categories: sample-posts
thumbnail: assets/img/enrichment_analysis.png
---

> Enrichment analysis is common, but is it done properly?

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/enrichment_analysis.png" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/enrichment_analysis.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Image from Cluster profiler showing significantly enriched biological processes
</div>
Let's dive in.

If you've spent time in genomics data analysis, you've likely encountered a list of genes you wanted to understand biologically. This is a common interest for biologists after a sequencing experiment or analysis.
Overrepresentation analysis (ORA) is a frequently employed method, but it is often prone to inaccuracies due to the presence of many false positives in the results( reference in the literature). So, what exactly is overrepresentation analysis (ORA)?

ORA aims to determine if established biological functions or gene sets are disproportionately represented in a list generated through experimentation. It involves comparing an experimentally derived gene list to a database of gene sets with known functions. The goal is to identify whether certain known biological functions are significantly overrepresented in the experimentally derived gene list.
Enrichment analysis has become widely accessible, leading to the development of numerous packages and tools for simplified analysis. However, some users may input their gene lists without a suitable background gene set for comparison, potentially resulting in false positive enrichments.

What is a background gene set?

The choice of background genes is critical as it determines which functionally enriched gene sets might appear overrepresented in our gene list. It's important to recognize that altering this background selection can significantly impact our analysis results.

Let's delve into a scenario: You conduct an RNA sequencing experiment on cancer cells, yielding a list of differentially expressed genes. For enrichment analysis, you consider two cases:
1. Default Background: Using all genes in the genome as your background, you identify 500 terms with few of them related to cancer.
2. User-Defined Background: Employing a user-defined background limited to genes found in cancer tissue, you now identify 300 relevant terms.
   
> This comparison highlights the impact of background gene selection on the enrichment analysis results, with the user-defined background providing a more contextually meaningful outcome.
The improved relevance of terms in the second analysis is indeed primarily attributed to the choice of background genes. Using a background set that closely matches the context of your experiment, such as genes found in cancer tissue, increases the likelihood of identifying biologically meaningful enrichments.

The misconception that all genes in the genome should be used as a background is a common one. Many popular tools do allow this option, and users may default to it because they might not fully understand the underlying statistical tests. Often, the desire to obtain relevant terms aligned with their hypothesis takes precedence.
This underscores the importance of educating users about the significance of selecting an appropriate background gene set in enrichment analysis to ensure more meaningful and accurate results.
An alternative approach, which is both useful and recommended, is to use the intersection of the genes measured in the tissue of interest and the genes annotated in the gene sets. This strategy enhances the relevance of the background gene set by focusing on genes that are actually expressed or relevant in your specific experimental context. It can lead to more precise and biologically meaningful enrichment analysis results compared to using all genes in the genome as the background.

Another useful or proposed alternative to not using all the genes in the genome is to use an intersection of the genes measured in the tissue of interest and genes annotated in the gene sets.
This post is a call to bring more awareness to understanding the concept of statistical assumption being tested before applying bioinformatics tools and software.
While enrichment analysis is a common practice, the critical aspect of selecting appropriate background genes is often overlooked. This post serves as a vital reminder to maintain awareness of the underlying statistical assumptions when applying bioinformatics tools, especially in the context of enrichment analysis. This heightened awareness can lead to more accurate and meaningful scientific discoveries.

References:
[Thread on twitter](https://twitter.com/mdziemann/status/1626407797939384320)
[NCBI](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4561415/)

