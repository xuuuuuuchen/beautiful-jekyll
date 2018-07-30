---
layout: post
published: Ture
category: "Image Registration"
title: Yuru Pei 2017 (30 Jul 2018 Reading Notes II)
subtitle:  Non-rigid Craniofacial 2D-3D Registration Using CNN-Based Regression
image: https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRAUYBdlX5AoNbjJ9TbuGN9Wry_ceoFoqB4a7hPEUGI86a6XYdeog

tags: [Reading Notes, Convolutional Neural Network, Image Registration]
---

**Title:** ssEMnet: Serial-Section Electron Microscopy Image Registration Using a Spatial Transformer Network with Learned Features [Paper Link](https://arxiv.org/abs/1707.07833)

**Authors:** Yuru Pei, Yungeng Zhang, Haifang Qin, Gengyu Ma, Yuke Guo, Tianmin Xu, Hongbin Zha

**Association:** Key Laboratory of Machine Perception (MOE), Department of Machine Intelligence, Peking University, Beijing, China

**Submission:** Sep 2017

![](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRAUYBdlX5AoNbjJ9TbuGN9Wry_ceoFoqB4a7hPEUGI86a6XYdeog) 



## Image Registration Background

[[My Literature Review]](https://xuuuuuuchen.github.io/LiteratureReview_ImageRegistration/)


## Motivation 1
due to its image characteristics: 
1. large and irregular tissue deformations with artifacts (史前古器物；人工产品) such as dusts and folds
2. drifting for long image sequences alignment
3. difficulty in finding the optimal alignment parameters
4. lack of global regularization and complicated parameter tuning

## Motivation 2
recent advances in deep neural networks:
1. Convolutional neural networks and their variants have shown potential by largely outperforming conventional computer vision algorithms
2. Spatial Transformer Networks (Max Jaderberg) uses a differentiable network module inside a CNN to overcome the drawbacks of CNNs (i.e., lack of scale- and rotation-invariance).


## Contributions

1. a novel deep network model specifically designed **for ssEM image registration**.
2. a novel combination of an STN and a convolutional autoencoder that generates a deformation map (i.e., vector map) for the entire image alignment via backpropagation of the network.
3. propose a feature-based image similarity measure
4. can easily extend to various applications by employing different feature encoding networks.


## Method 


**1. Feature Generation Using a Convolutional Autoencoder**

[goal] compute similarities between adjacent EM sections

[consists of] **a convolutional encoder** comprised of convolutional layers with ReLU activations and **a deconvolutional decoder** comprised of deconvolutional layers with ReLU activations

[output]  similarities between adjacent EM sections

[architecture] 

![](https://github.com/xuuuuuuchen/xuuuuuuchen.github.io/blob/master/img/2018-07-30-readnote/1.png?raw=true) 

[results] Figure 1 shows that our autoencoder feature-based registration gen-erates more accurate results compared to the conventional pixel intensity-based registration, i.e., (d) shows the smaller **normalized cross correlation** (NCC) error between aligned images than (c).

![](https://github.com/xuuuuuuchen/xuuuuuuchen.github.io/blob/master/img/2018-07-30-readnote/2.png?raw=true) 

**2. Deformable Image Registration Using a STN**

[goal] is intended to find the proper deformation of the input image via an ST by minimizing the registration error measured by the pre-trained autoencoder.

[architecture] 

![](https://github.com/xuuuuuuchen/xuuuuuuchen.github.io/blob/master/img/2018-07-30-readnote/3.png?raw=true) 


{: .box-warning}
**However:** the resolution of vector map v is usually coarser (简略的) than that of the input image.

need **smooth interpolation** of a coarse vector map to obtain a perpixel moving vector for actual deformation of the moving image.


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



**3. empty space mask**

[goal] To accumulate the registration error only within the image after deformation

After image deformation, we collect the pixels outside the valid image region and make a binary mask image. 
We resize this mask image to match the size of the autoencoder feature map using a bilinear interpolation.

**4. loss drop**

[goal] prevented local minimums and obtained smoother registration results.

first dropped the top 50% of high error features, and then reduced the dropping rate by half per every iteration. 


## Performance

![](https://github.com/xuuuuuuchen/xuuuuuuchen.github.io/blob/master/img/2018-07-30-readnote/4.png?raw=true) 

## Ref.

