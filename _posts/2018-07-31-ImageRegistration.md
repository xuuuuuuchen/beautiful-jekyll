---
layout: post
published: Ture
category: "Image Registration"
title: Literature Review of Image Registration
image: https://www.wikihow.com/images/9/99/Do-a-Literature-Review-Step-13-Version-2.jpg

tags: [Literature Review, Image Registration]
---

![](https://www.wikihow.com/images/9/99/Do-a-Literature-Review-Step-13-Version-2.jpg) 


## Literature Review



**Introduction**

introducing two very important concepts that will prove crucial in understanding the inner workings of the Spatial Transformer layer. 



## Deep Learning

for image registration, deep learning is very promising because
1) is an unsupervised learning approach that does not require ground truth
2) uses a hierarchical deep architec- ture to infer complex nonlinear relationships
3) is completely data driven and not based on handcrafted feature selection
4) can quickly and efficiently compute the hierarchical feature representation for any image patch in the testing data given the trained hierarchical deep architecture (or network).


## Previous Methods

1. Intensity-based feature selection methods:


2. Handcrafted features, such as geometric moment invariants [15] or Gabor filter:

3. Supervised learning-based methods:

4. unsupervised learning-based feature selection methods:




Wu et al. [[Reading Note]](https://xuuuuuuchen.github.io/2018-07-31-readnote/) [[Paper]](https://ieeexplore.ieee.org/document/7314894/): "used a convolutional stacked auto-encoder (**CAE**) to extract features from fixed and moving images that are subsequently used in conventional deformable image registration algorithms. However, the CAE is decoupled from the image registration task and hence, it does not necessarily extract the features most descriptive for image registration. The training of the CAE was unsupervised, but the registration task was not learned end-to-end."

Miao et al. [[Reading Note]](https://xuuuuuuchen.github.io/2018-07-23-readnote-add/) "used a convolutional neural network (ConvNet) regressor to predict a transformation matrix for rigid registration of synthetic 2D to 3D images. "

Liao et al. [[Paper]](https://arxiv.org/abs/1611.10336) "used a ConvNet for intra-patient rigid registration of CT to cone-beam CT applied to either cardiac or abdominal images. "

"Both registration methods (Miao et al. and Liao et al.) were supervised: for training, transformation parameters were generated, which is task specific and highly challenging."

Jaderberg et al. [[Reading Note]](https://xuuuuuuchen.github.io/2018-07-26-readnote/) [[Paper]](https://arxiv.org/abs/1506.02025)  *(‎Cited by 901)*: " introduced the spatial transformer network (STN) that can be used as a **building block that aligns input images in a larger network** that performs a particular task. By training the entire network end-to-end, the embedded STN deduces optimal alignment for solving that specific task. "
"**However, alignment is not guaranteed**, and it is only performed when required for the task of the entire network. The STNs were used for affine transformations, as well as deformable transformations using thin-plate splines. However, an STN needs many labeled training examples, and to the best of our knowledge,** **have not yet been used in medical imaging**."

