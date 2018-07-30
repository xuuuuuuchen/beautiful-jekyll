---
layout: post
published: Ture
category: "Image Registration"
title: 30 Jul 2018 Reading Notes II (Non rigid Craniofacial 2D 3D Registration Using CNN Based Regression)
subtitle: Yuru Pei et al Sep 2017
image: https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRAUYBdlX5AoNbjJ9TbuGN9Wry_ceoFoqB4a7hPEUGI86a6XYdeog

tags: [Reading Note, Convolutional Neural Network, Image Registration]
---

**Title:** ssEMnet: Serial-Section Electron Microscopy Image Registration Using a Spatial Transformer Network with Learned Features [Paper Link](https://arxiv.org/abs/1707.07833)

**Authors:** Yuru Pei, Yungeng Zhang, Haifang Qin, Gengyu Ma, Yuke Guo, Tianmin Xu, Hongbin Zha

**Association:** Key Laboratory of Machine Perception (MOE), Department of Machine Intelligence, Peking University, Beijing, China

**Submission:** Sep 2017

![](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRAUYBdlX5AoNbjJ9TbuGN9Wry_ceoFoqB4a7hPEUGI86a6XYdeog) 

## Background




Wu et al. [[Paper]](https://ieeexplore.ieee.org/document/7314894/): "used a convolutional stacked auto-encoder (**CAE**) to extract features from fixed and moving images that are subsequently used in conventional deformable image registration algorithms. However, the CAE is decoupled from the image registration task and hence, it does not necessarily extract the features most descriptive for image registration. The training of the CAE was unsupervised, but the registration task was not learned end-to-end."

Miao et al. [[Reading Note]](https://xuuuuuuchen.github.io/2018-07-23-readnote-add/) "used a convolutional neural network (ConvNet) regressor to predict a transformation matrix for rigid registration of synthetic 2D to 3D images. "

Liao et al. [[Paper]](https://arxiv.org/abs/1611.10336) "used a ConvNet for intra-patient rigid registration of CT to cone-beam CT applied to either cardiac or abdominal images. "

"Both registration methods (Miao et al. and Liao et al.) were supervised: for training, transformation parameters were generated, which is task specific and highly challenging."

Jaderberg et al. [[Reading Note]](https://xuuuuuuchen.github.io/2018-07-26-readnote/) [[Paper]](https://arxiv.org/abs/1506.02025)  *(‎Cited by 901)*: " introduced the spatial transformer network (STN) that can be used as a **building block that aligns input images in a larger network** that performs a particular task. By training the entire network end-to-end, the embedded STN deduces optimal alignment for solving that specific task. "
"**However, alignment is not guaranteed**, and it is only performed when required for the task of the entire network. The STNs were used for affine transformations, as well as deformable transformations using thin-plate splines. However, an STN needs many labeled training examples, and to the best of our knowledge,** **have not yet been used in medical imaging**."


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

