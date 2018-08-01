---
layout: post
published: Ture
category: "Image Registration"
title: Basic Knowledge of Image Registration
subtitle: Scalable High-Performance Image Registration Framework by Unsupervised Deep Feature Representations Learning
image: https://ai2-s2-public.s3.amazonaws.com/figures/2017-08-08/e254ed51e3dfe438a36bb027aa75793f78f556c0/4-Figure2-1.png
tags: [Literature Review, Image Registration]
---

![](https://www.wikihow.com/images/9/99/Do-a-Literature-Review-Step-13-Version-2.jpg) 

**Title:** An Artificial Agent for Robust Image Registration (Thirty-First AAAI Conference on Artificial Intelligence (AAAI-17)) [Paper Link](https://arxiv.org/abs/1611.10336)

**Authors:** Rui Liao, Shun Miao, Pierre de Tournemire, Sasa Grbic, Ali Kamen, Tommaso Mansi, Dorin Comaniciu

**Association:** Technology Center, Medical Imaging Technologies Siemens Medical Solutions USA

**Submission:** 2017

## Background of Deep Learning in Medical Image Analysis

[NEED A Reading Notes]](https://xuuuuuuchen.github.io/2018-08-01-DeepLearninginMedicalImageAnalysis/)

## Image Registration Background

[Basic Knowledge]](https://xuuuuuuchen.github.io/2018-07-31-ImageRegistration-basic/)

[[Literature Review]](https://xuuuuuuchen.github.io/2018-07-31-ImageRegistration/)

## Slice-to-volume Medical Image Registration Background

[NEED A Reading Notes]](https://xuuuuuuchen.github.io/2018-08-01-ImageRegistration-2D-3D/)


## Motivation of 3-D medical image registration

to recover correspondences between two 3-D images acquired into the same coordinate system from

1. different patients

2. the same patient at different time

3. different modalities e.g. Computed Tomography (CT), Magnetic Resonance Imaging (MRI), Positron Emission Tomog- raphy (PET) etc.


## Contributions

0. decompose the registration task into a sequence of (often easier) classification problems, i.e. finding the best action among a limited set of possible solutions to improve the alignment. Repeating this process can result in a converging solution. 

1. train the intelligent agent in a greedy supervised fashion, which is a magnitude more efficient with only a small fraction of the memory footprint than in standard DRL setup, where the agent learns through repeated trial and errors

2. propose an effective data augmentation and sampling strategy so that the agent could be trained robustly using only a small number of labelled training pairs available from patients

3. propose a hierarchical registration framework relying on the trained networks from the coarse 粗糙的 image layer to register successively the more refined (higher resolution) image layers.

## Method 

**Method 1. Feature Generation Using a Convolutional Autoencoder**

**[GOAL]** compute similarities between adjacent EM sections

**[Architecture]** **a convolutional encoder** comprised of convolutional layers with ReLU activations and **a deconvolutional decoder** comprised of deconvolutional layers with ReLU activations

![](https://github.com/xuuuuuuchen/xuuuuuuchen.github.io/blob/master/img/2018-07-30-readnote/1.png?raw=true) 

**[Output]**  similarities between adjacent EM sections

**[Results]** Figure 1 shows that our autoencoder feature-based registration gen-erates more accurate results compared to the conventional pixel intensity-based registration, i.e., (d) shows the smaller **normalized cross correlation** (NCC) error between aligned images than (c).

![](https://github.com/xuuuuuuchen/xuuuuuuchen.github.io/blob/master/img/2018-07-30-readnote/2.png?raw=true) 


**Method 2. Deformable Image Registration Using a STN**

**[GOAL]** is intended to find the proper deformation of the input image via an ST by minimizing the registration error measured by the pre-trained autoencoder.

**[Architecture]**

![](https://github.com/xuuuuuuchen/xuuuuuuchen.github.io/blob/master/img/2018-07-30-readnote/3.png?raw=true) 


{: .box-warning}
**However:** the resolution of vector map v is usually coarser (简略的) than that of the input image.

Need **smooth interpolation** of a coarse vector map to obtain a perpixel moving vector for actual deformation of the moving image.


**smooth deformable transform:**
1. thin plate spline (TPS) 
2. bilinear (with better results compared to the TPS) [[Reading Note]](https://xuuuuuuchen.github.io/2018-07-26-readnote/)
3. bicubic
4. B-spline
5. ...

![](https://github.com/xuuuuuuchen/xuuuuuuchen.github.io/blob/master/img/2018-07-30-readnote/5.png?raw=true) 

To increase the robustness of alignment, extend the objective function (Eq.4) to leverage multiple neighbor sections.
**Let** the moving image be I0, its neighbor reference n images be I1 to In, and their corresponding weights be wi.

![](https://github.com/xuuuuuuchen/xuuuuuuchen.github.io/blob/master/img/2018-07-30-readnote/6.png?raw=true) 

(Eq. 5) combines the registration errors across neighbor images, which can lessen strong registration errors from images with artifacts and avoid large deformation. M(T) the autoencoder feature map using a bilinear interpolation.


**Method 3. empty space mask**

**[GOAL]** To accumulate the registration error only within the image after deformation

After image deformation, we collect the pixels outside the valid image region and make a binary mask image. 
We resize this mask image to match the size of the autoencoder feature map using a bilinear interpolation.

**Method 4. loss drop**

**[GOAL]** Prevented local minimums and obtained smoother registration results.

First dropped the top 50% of high error features, and then reduced the dropping rate by half per every iteration. 


## Performance

![](https://github.com/xuuuuuuchen/xuuuuuuchen.github.io/blob/master/img/2018-07-30-readnote/4.png?raw=true) 


