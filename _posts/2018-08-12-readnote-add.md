---
layout: post
published: Ture
category: "Image Registration"
title: Guha Balakrishnan 2018 (12 Aug 2018 Reading Notes II)
subtitle: (CVPR 2018) An Unsupervised Learning Model for Deformable Medical Image Registration
image: https://www.groundai.com/media/arxiv_projects/91360/x7.png.750x0_q75_crop.png
tags: [Reading Notes, 3D MR brain scans, Image Registration]
---

**Title:** An Unsupervised Learning Model for Deformable Medical Image Registration [Paper Link](https://arxiv.org/abs/1802.02604)

**Authors:** Guha Balakrishnan et al.

**Association:** MIT

**Submission:** 2018

![](https://www.groundai.com/media/arxiv_projects/91360/x7.png.750x0_q75_crop.png) 
.................................................................................................................................

## >>> Background of Deep Learning in Medical Image Analysis

[[NEED A Reading Notes]](https://xuuuuuuchen.github.io/2018-08-01-DeepLearninginMedicalImageAnalysis/)

## >>> A Review: Robot-Assisted Endovascular Catheterization Technologies: 

[[NEED A Reading Notes]](https://xuuuuuuchen.github.io/Robot-AssistedEndovascularCatheterizationTechnologies/)

.................................................................................................................................

## >>> Image Registration Basic Knowledge

[[Basic Knowledge]](https://xuuuuuuchen.github.io/2018-07-31-ImageRegistration-basic/)

## >>> Image Registration Literature Review

[[Literature Review]](https://xuuuuuuchen.github.io/2018-07-31-ImageRegistration/)

## >>> Slice-To-Volume Medical Image Registration Background

[[NEED A Reading Notes]](https://xuuuuuuchen.github.io/2018-08-01-ImageRegistration-2D-3D/)

.................................................................................................................................


## Motivation


## Contributions

**(0)** define registration as a parametric function, and optimize its parameters given a set of images from a collection of interest. Given

**(1)** (OPEN SOURCE) code is available at https://github.com/balakg/voxelmorph


**(2)** present a learning-based solution requiring no supervised information such as ground truth correspon- dences or anatomical landmarks during training,

**(3)** propose a CNN function with parameters shared across a population, enabling registration to be achieved through a function evaluation

**(4)** enables parameter optimization for a variety of cost functions, which can be adapted to various tasks.

## Methods

![](https://github.com/xuuuuuuchen/xuuuuuuchen.github.io/blob/master/img/2018-08-12-readnote/4.png?raw=true) 

## Loss function


consisting of two components:

- penalizes differences in appearance **L_sim**

And set **L_sim** to the negative local cross-correlation of M(φ) and F.

![](https://github.com/xuuuuuuchen/xuuuuuuchen.github.io/blob/master/img/2018-08-12-readnote/5.png?raw=true) 



- penalizes local spatial variations in φ **L_smooth**


![](https://github.com/xuuuuuuchen/xuuuuuuchen.github.io/blob/master/img/2018-08-12-readnote/6.png?raw=true) 



## Performance


![](https://github.com/xuuuuuuchen/xuuuuuuchen.github.io/blob/master/img/2018-08-12-readnote/7.png?raw=true) 


