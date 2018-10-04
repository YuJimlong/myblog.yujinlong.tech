---
title: 'Prokka: prokaryotic genome annotation'
author: Yu Jinlong
date: '2018-10-04'
slug: prokka-prokaryotic-genome-annotation
categories:
  - Linux
tags:
  - annotation
lastmod: '2018-10-04T09:58:52+08:00'
keywords: []
description: ''
comment: no
toc: no
autoCollapseToc: no
contentCopyright: no
reward: no
mathjax: no
---
Prokka is a fast and accurate prokaryotic genome annotation system under UNIX platform.  

<!--more-->

# INSTALL

```
conda install prokka  
```

# Simple Usage  

```
prokka genome.fasta --outdir outputdir 
```

# Details  
> Prokka is a stand-alone software that connects several packages together.  

- For CDS prediction, it uses Prodigal  
- For rRNA prediction, it uses RNAmmer  
- For rRNA prediction, it uses Aragorn  
- For Signal peptides prediction, it uses SignalIP  
- For ncRNA it uses Infernal  

As a result, if you wanna predict 16srRNA sequence in your genome, don't bother to use RNAmmer if Prokka didn't give you a result. The two packages share the same code.  

# Comparing with other platforms  
According to the [paper](https://academic.oup.com/bioinformatics/article/30/14/2068/2390517), prokka produced an overall better annotation than RAST and xBase2.  
However, according to my experience, RAST sometimes predict annotations that prokka didn't produce, although the output of prokka is more friendly because it provides the gene name while RAST didn't.  
As a result, I prefer to combine the result of both source.  

> for detailed infromation and how it works, please visit [github](https://github.com/tseemann/prokka)

