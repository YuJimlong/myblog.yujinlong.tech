---
title: 'Bioconda: A package management center for Linux'
author: Yu Jinlong
date: '2018-10-02'
slug: bioconda-a-package-management-center-for-linux
categories:
  - Linux
tags: []
lastmod: '2018-10-02T20:15:47+08:00'
keywords: []
description: ''
comment: no
toc: no
autoCollapseToc: no
contentCopyright: no
reward: no
mathjax: no
---
For greenhands in bioinformatics, the biggest challenge is to install bioinformatic software in the Linux system.  
Here comes **bioconda**, a software that resolve most of the difficulty for beginners when dealing with bioinformatic software.  
<!--more-->
# How to install  
Open your bash, type the following
```
wget https://repo.continuum.io/miniconda/Miniconda2-latest-Linux-x86_64.sh 
bash Miniconda2-latest-Linux-x86_64.sh 
source ~/.bashrc


```
# Add channels

```
conda config --add channels conda-forge
conda config --add channels defaults
conda config --add channels r
conda config --add channels bioconda
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/bioconda/
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge/
```
# Usage

All of the software are installed under the directory:  ```~/miniconda2/bin/```

```
conda install -y bwa
# conda will automatically install the latest version if you don't specify the version number.  
conda install -y bwa=0.7.15
# if you wanna a specified version, you should type the software name like this.  
conda install -y hmer2 htseq htslib igvtools  
# a list of software can be installed simultaneaously.  
```
# Creat an environment  
```
conda  create  -n  aligners
# now we have a environment named "aligners"
```
# Activate your environment 
```
source avtivete aligners  
conda install -y hisat2  
#  all of the software are installed under the directory :$HOME/miniconda2/envs/aligners/bin/
```

# Quit your environment   
```
source deactivate 
```
# Other usage  
```
conda list 
# list all the installed packages  
conda uninstall star
conda remove star  
# uninstall the software.  
```

> for detailed information
[a guidance for conda usage](http://blog.sciencenet.cn/blog-2970729-1074395.html)
[a guidance for conda installation](https://mp.weixin.qq.com/s?__biz=MzI2MjA1MDQxMg==&mid=2649707327&idx=1&sn=3dd608d5ac32725bfbc44563e961442c&chksm=f24af43cc53d7d2af7aaf9073f846753fbd92267b858a53f1be0bd8bd45115636a8857c1b001&scene=21#wechat_redirect)