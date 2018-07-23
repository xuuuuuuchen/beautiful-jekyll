---
layout: post
published: Ture
category: "Image Registration"
title: 23 Jul 2018 Reading Note add
subtitle: A CNN Regression Approach for Real-Time 2D 3D Registration
image: https://ai2-s2-public.s3.amazonaws.com/figures/2017-08-08/0b3369b950ca9b273b24a72b6023981d31b68ae2/2-Figure2-1.png
tags: [Reading Note, Convolutional Neural Network, Image Registration]
---

**Title:** Quicksilver: Fast predictive image registration – A deep learning approach [Paper Link](https://arxiv.org/abs/1703.10908)

**Authors:** Shun Miao, Z. Jane Wang, Rui Liao

**Association:** Department of Electrical and Computer Engineering, University of British Columbia, Vancouver, Canada

**Submission:** May 2016

![](https://ai2-s2-public.s3.amazonaws.com/figures/2017-08-08/0b3369b950ca9b273b24a72b6023981d31b68ae2/2-Figure2-1.png) 

{: .box-note}
**Image registration** is a key component for medical image analysis to provide spatial correspondences.

## Contributions

**(0)** introduces Quicksilver, a fast deformable image registration method.

**(1)** propose a deep regression model to predict defor-
mation parameters using image appearances in a time-efficient manner.

**(2)** focus on predictions for the Large Deformation Diffeomorphic Metric Mapping (LDDMM) model.

**(3)** introduce a new correction network which greatly increases the prediction accuracy of an already existing prediction network. 

**(4)** open-source  [https://github.com/rkwitt/quicksilver](https://github.com/rkwitt/quicksilver) 

![](https://ars.els-cdn.com/content/image/1-s2.0-S1053811917305761-gr1.jpg) 

## Background

Image registration = an optimization problem = optimizing the parameters of a transformation model

**Process:**
1. Detect features.
An image feature is any protion of an image that can potentially be identified. Features can be points, lines, or corners, etc.

2. Match corresponinging features.

3. Infer geometric transformation.
Fom the sets of matched-feature pairs, a geometric transformation function is inferred that maps features in one image onto the locations of the matching features in the other.

4. Use the geometric transformation to align one image with the other.

**type of transformation**

- Low-dimensional parametric registration models: affine, rigid
- High-dimensionalparametric registration models
- Non-parametric parametric registration models

{: .box-note}
**However,**  Non-parametric parametric registration models have a very large numbers of parameters. Therefore, numerical optimzation to solve the registration problems becomes computationally costly, even with acceleration by graphics processing units (GPUs).


## Motivation

**(1)**  "achieve the best possible agreement between a transformed source and a target image, subject to transformation constraints."



## Network Design

![](https://ars.els-cdn.com/content/image/1-s2.0-S1053811917305761-gr2.jpg) 

" Fig. 2. 3D (probabilistic) network architecture. The network takes two 3D patches from the moving and target image as the input, and outputs 3 3D initial momentum patches (one for each of the x; y and z dimensions respectively; for readability, only one decoder branch is shown in the figure). In case of the deterministic network, see Sec. 2.2.1, the dropout layers, illustrated by , are removed. Conv: 3D convolution layer. Conv⊺: 3D transposed convolution layer. Parameters for the Conv and Conv⊺ layers: In: input channel. Out: output channel. Kernel: 3D filter kernel size in each dimension. Stride: stride for the 3D convolution. Pad: zero-padding added to the boundaries of the input patch. Note that in this illustration B denotes the batch size."

![](https://ars.els-cdn.com/content/image/1-s2.0-S1053811917305761-gr3.jpg) 

"Fig. 3. The full prediction þ correction architecture for LDDMM momenta. First, a rough prediction of the initial momentum, mLP, is obtained by the prediction network (LP) based on the patches from the unaligned moving image, Mand target image, T, respectively. The resulting deformation maps Φ?1 and Φ are computed by shooting. Φ is then applied to the target image to warp it to the space of the moving image. A second correction network is then applied to patches from the moving image M and the warped target image T∘Φ to predict a correction of the initial momentum, mC in the space of the moving image, M. The final momentum is then simply the sum of the predicted momenta, m ¼ mLP þmC, which parameterizes a geodesic between the moving image and the target image."
2.4.

## Limitations


*


## Performance


*


## Other Useful Info.

Object Detection [helpful slides link](https://www.slideshare.net/xavigiro/object-detection-d2l5-insightdcu-machine-learning-workshop-2017)
(D2L5 Insight@DCU Machine Learning Workshop 2017)



