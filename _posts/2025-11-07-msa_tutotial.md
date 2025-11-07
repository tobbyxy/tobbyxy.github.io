
---
layout: post
title: understanding multiple sequence alignment
date: 2025-11-07 20:01:00
description: 
tags: bioinformatics
categories: post
thumbnail: 
---

Alignment is the foundation of bioinformatics. BLAST used my almost everyone in the field is an alignment algorithm. There are different kinds of alignment: pairwise, local, global, multiple sequence alignment. Over the years multiple alignment tools have been designed with different assumptions, goals, parameters. With that in mind, choosing an alignment tool for your task can be overwhelming. when do you know an alignment is good or bad?

Most multiple sequence alignment tools assume an evolutionary relationship (homology) between sequences of interest. There are majors ones like Mafft, Clustal-omega and Muscle. The goal of this tutorial is to see how they work and usecase for them.

mafft uses a progessive alignment strategy from leaves to root
clustalo uses hidden markov model (probabilistic sequence modelling) and can be more accurate
Muscle

we will follow data from this phylogenetic course of amino acid sequences.

My observation:
There is no free meal, you should check the results of alnment for manual inspection. 
clustalo or HMM derivative tries as much as possible to resolve gaps differently. i think if there is a gap, it will include any other gaps close to that position, preventing single gaps where possible. maximises gap extension (sometimes this can happen at a cost)
you can align an alignment using profiles (which are just probability summary of nucleotide occurence at a particular position)

