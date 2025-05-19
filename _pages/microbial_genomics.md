---
layout: page
permalink: /microbial_genomics/
title: microbial genomics
description: genomics Tools and their assumptions in my experience.
nav: True
nav_order: 4
---

## Panaroo
### Tonkin-Hill, G., MacAlasdair, N., Ruis, C. et al. "Producing polished prokaryotic pangenomes with the Panaroo pipeline." Genome Biol 21(180) (2020). https://doi.org/10.1186/s13059-020-02090-4
panaroo is a graph algorithm for pangenome reconstruction that aims to improve genome annotation calls by correcting for sources of error from fragmented assemblies, misassemblies. it takes in gff file as input and outputs pangenome reference, gene presence absence file.
one its assumptions is that the genomes are closely related to each other i.e the same species.

## Piggy
Pangenome analysis tools for intergenic regions in bacteria.

gene prediction
## Balrog

gene annotation
## prokka
## bakta

gene clustering
## ggcaller 
ggCaller combines gene prediction, functional annotation, and clustering into a single workflow using population-wide de Bruijn graphs, removing redundancy in gene annotation and resulting in more accurate gene predictions and orthologue clustering

## PCA and GWAS
ibg.colorado.edu

## pyseer
kmer based GWAS method that allows for different methods of association test.
Unitig and mixed effect is recommended

We wish to test the hypothesis $$ b_j = 0 $$ within the linear mixed model:

\begin{equation}
\label{eq:lmm}
\mathbf{y} = \mathbf{x}_j b_j + \mathbf{g} + \mathbf{e}
\end{equation}

where:  
- \( \mathbf{y} \) is a length-\( n \) phenotype vector,  
- \( \mathbf{x}_j \) is the vector encoding alleles at the \( j \)th variant,  
- \( \mathbf{g} \sim \mathcal{N}(0, \sigma_g^2 \mathbf{K}) \) is a vector of random genetic effects,  
- \( \mathbf{e} \sim \mathcal{N}(0, \sigma_e^2 \mathbf{I}_n) \) is a vector of environmental noise,  
- \( \mathbf{I}_n \) is the \( n \times n \) identity matrix.

We test whether the fixed effect coefficient \( b_j \) associated with the variant \( \mathbf{x}_j \) is statistically different from zero, indicating an association with the phenotype


## treeWas
A phylogenetic based GWAS microbial method that infers both the ancestral phenotype and genotype states at each internal node of the phylogeny, before computing three association test statistics:


Terminal Score: It measures sample-wide phenotype-genotype associations between leaves of the phylogeny.
Simultaneous Score: It measures parallel changes in both phenotype and genotype on phylogeny branches.
Subsequent Score: It measures the proportion of the tree within which genotype and phenotype ‘co-exist’. It is equivalent to integrating association scores over all tree nodes.
For each sore, a significance threshold was estimated from null simulations of genetic data at 10 times as many sites as the observed dataset.

## phylogeny reconstruction

iqtree
ClonalFrameML


## Resources
Cogniterra Bioinformatics Algorithm
Phylogenetics in the genomic era
Mortimer Lab page
John Lees web page https://www.bacpop.org/research/
Gtonkinhill https://gthlab.au/about/



