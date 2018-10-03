---
title: 'BLAST: build your own blast on your laptop'
author: Yu Jinlong
date: '2018-10-02'
slug: blast-build-your-own-blast-on-your-laptop
categories:
  - Linux
tags: []
lastmod: '2018-10-02T20:37:36+08:00'
keywords: []
description: ''
comment: no
toc: no
autoCollapseToc: no
contentCopyright: no
reward: no
mathjax: no
---
**B**asic **L**ocal **A**lignment **S**earch **T**ool  ([BLAST](https://blast.ncbi.nlm.nih.gov/Blast.cgi))  is one of the most commonly used bioinformatic software for researchers in the filed of biology and medicine.  
It is very useful to find homology of a specific sequence, be it AA(amino acid) or NT(nucliotide) sequence.  
However, most of the users don't know that BLAST can be installed under their personal computer.  
<!--more-->
# How to install  
First, make sure you have installed **conda** in your computer.  
Just type the following codes in you terminal, conda will perform all the task for you.  
```
conda install -y blast
```

# To build a database for query 
```
makeblastdb -in Os.fa -dbtype prot -title Os_protein -parse_seqids -out Os_pro_db
```
- `-in` is the input file, it is a collection of fasta sequence that you want to make into a database for query latter.  
- `-title` is the name of the database, you will use them when make query later.  
- `-out` is the output file name, we don't deal with the file most of the time, so just give the same file name with the **title**.  

# Make a query  

Query is also known as alignment.  
It's the proccess of aligning the query sequence to the whole database that you build before.  
Blast have serveral types of query mode  

- blastn:Nucleotide-Nucleotide    
- blastx:Translated Query-Protein Subject  
- blastp:Protein-Protein  
- tblastn:Protein Query-Translated Subject  
- tblastx:Translated Query-Translated Subject  

take the most used blastn for example  

```
blastn -query query_sequence.fna -db your_database_title -out test.out -evalue 0.001 -outfmt 6
```
```
 -outfmt <String>
   alignment view options:
     0 = Pairwise,
     1 = Query-anchored showing identities,
     2 = Query-anchored no identities,
     3 = Flat query-anchored showing identities,
     4 = Flat query-anchored no identities,
     5 = BLAST XML,
     6 = Tabular,
     7 = Tabular with comment lines,
     8 = Seqalign (Text ASN.1),
     9 = Seqalign (Binary ASN.1),
    10 = Comma-separated values,
    11 = BLAST archive (ASN.1),
    12 = Seqalign (JSON),
    13 = Multiple-file BLAST JSON,
    14 = Multiple-file BLAST XML2,
    15 = Single-file BLAST JSON,
    16 = Single-file BLAST XML2,
    17 = Sequence Alignment/Map (SAM),
    18 = Organism Report
```