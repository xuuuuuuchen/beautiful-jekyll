---
layout: post
published: Ture
category: "Image Registration"
category: "Deep Learning"
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


## Contributions

**(1)** A CNN regression approach, referred to as Pose Estimation via Hierarchical Learning (PEHL), is proposed to achieve real-time 2-D/3-D registration with a large capture range and high accuracy.

**(2)** to train CNN regressors to recover the mapping **from the DRR** and X-ray images to the difference of their underlying transformation parameters. 

{: .box-note}
**mapping** is highly complex and training regressors to recover the mapping is far from being trivial (unimportant)

**(3)** First simplifying the non-linear relationship using the following three algorithmic strategies: Localimage residual(LIR), Parameter space partitioning (PSP), Hierarchical parameter regression (HPR)

**(4)** Then capturing the mapping using CNN regressors with a strong non-linear modeling capability.



![](https://ars.els-cdn.com/content/image/3-s2.0-B978012810408800016X-gr001.jpg) 

## Digitally Reconstructed Radiograph (DRR)

![](https://media.springernature.com/lw785/springer-static/image/art%3A10.1186%2Fs12938-017-0353-8/MediaObjects/12938_2017_353_Fig1_HTML.gif) 

![](https://image.slidesharecdn.com/presentation-100511175011-phpapp02/95/generation-of-planar-radiographs-from-3d-anatomical-models-using-the-gpu-3-728.jpg?cb=1273601116) 

![](https://image.slidesharecdn.com/presentation-100714114159-phpapp01/95/generation-of-planar-radiographs-from-3d-anatomical-models-using-the-gpu-6-728.jpg?cb=1279107927) 


## Motivation

**(1)** Intensity-based methods are known to be able to achieve high registration accuracy 
--- *“A comparison of 2D-3D intensity-based registration and feature-based registration for neurointerventions,” in Proc. MICCAI, 2002*,
two major drawbacks: (1) long computation time (2) small capture range (because intensity-based methods involve a large number of evaluations of the **similarity measure**, each requiring heavy computation in rendering the DRR)

**(2)** the similarity measures to be optimized in Intensity-based methods often highly **non-convex**, the optimizer **has a high chance of getting trapped into local maxima**, which leads to a small capture range of these methods.

## 3-D Transformation Parameterization

![](https://ai2-s2-public.s3.amazonaws.com/figures/2017-08-08/0b3369b950ca9b273b24a72b6023981d31b68ae2/2-Figure1-1.png) 
they parameterize the transformation by 3 in-plane and 3 out-of-plane transformation parameters

**in-plane transformation parameters:**2 translation parameters and 1 rotation parameter. 
The effects of in-plane transformation parameters are approximately 2-D rigid-body transformations. 

**Out-of-plane transformation parameters:**  1 out-of-plane translation parameter,
and 2 out-of-plane rotation parameters. 
The effects of out-of-plane translation and rotations are scaling and shape changes, respectively.



## X-Ray Imaging Model 


## Limitations


*


## Performance


*


## Other Useful Info.

Object Detection [helpful slides link](https://www.slideshare.net/xavigiro/object-detection-d2l5-insightdcu-machine-learning-workshop-2017)
(D2L5 Insight@DCU Machine Learning Workshop 2017)



