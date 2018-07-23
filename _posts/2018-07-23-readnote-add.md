---
layout: post
published: Ture
category: "Image Registration"
title: 23 Jul 2018 Reading Note add
subtitle: A CNN Regression Approach for Real-Time 2D 3D Registration
image: https://ai2-s2-public.s3.amazonaws.com/figures/2017-08-08/0b3369b950ca9b273b24a72b6023981d31b68ae2/2-Figure2-1.png
tags: [Reading Note, Convolutional Neural Network, Image Registration]
---

**Title:** A CNN Regression Approach for Real-Time 2D/3D Registration [Paper Link](https://ieeexplore.ieee.org/document/7393571/)

**Authors:** Shun Miao, Z. Jane Wang, Rui Liao

**Association:** Department of Electrical and Computer Engineering, University of British Columbia, Vancouver, Canada

**Submission:** May 2016

![](https://ai2-s2-public.s3.amazonaws.com/figures/2017-08-08/0b3369b950ca9b273b24a72b6023981d31b68ae2/2-Figure2-1.png) 

{: .box-note}
**Image registration** is a key component for medical image analysis to provide spatial correspondences.


| Supervised learning for 2-D/3-D registration | learning regressors for 2-D/3-D registration |
| :------ |:--- | 
| YOLO  | Faster R-CNN | 


 to


## Contributions

**(1)** A CNN regression approach, referred to as Pose Estimation via Hierarchical Learning (PEHL), is proposed to achieve real-time 2-D/3-D registration with a large capture range and high accuracy.

**(2)** to train CNN regressors to recover the mapping from the DRR and X-ray images to the difference of their underlying transforma- tion parameters. Such

**(3)** 

**(4)** 


![](https://ars.els-cdn.com/content/image/1-s2.0-S1053811917305761-gr1.jpg) 

## Digitally Reconstructed Radiograph (DRR)



## Motivation

**(1)** Intensity-based methods are known to be able to achieve high registration accuracy 
--- *“A comparison of 2D-3D intensity-based registration and feature-based registration for neurointerventions,” in Proc. MICCAI, 2002*,
two major drawbacks: (1) long computation time (2) small capture range (because intensity-based methods involve a large number of evaluations of the **similarity measure**, each requiring heavy computation in rendering the DRR)

**(2)** the similarity measures to be optimized in Intensity-based methods often highly **non-convex**, the optimizer **has a high chance of getting trapped into local maxima**, which leads to a small capture range of these methods.

## Network Design

## Limitations


*


## Performance


*


## Other Useful Info.

Object Detection [helpful slides link](https://www.slideshare.net/xavigiro/object-detection-d2l5-insightdcu-machine-learning-workshop-2017)
(D2L5 Insight@DCU Machine Learning Workshop 2017)



