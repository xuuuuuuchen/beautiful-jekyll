---
layout: post
published: Ture
category: "Literature Review"
title: Basic Knowledge of Image Registration
image: https://www.wikihow.com/images/9/99/Do-a-Literature-Review-Step-13-Version-2.jpg

tags: [Literature Review, Image Registration]
---

![](https://www.wikihow.com/images/9/99/Do-a-Literature-Review-Step-13-Version-2.jpg) 


## Basic Knowledge


**affine transformations**

https://kevinzakka.github.io/2017/01/10/stn-part1/
![](https://kevinzakka.github.io/assets/stn/affine.png) 

When an image undergoes an affine transformation such as a rotation or scaling, the pixels in the image get moved around. This can be especially problematic when a pixel location in the output does not map directly to one in the input image.

*To solve this problem:*

In the illustration below, you can clearly see that the rotation places some points at locations that are not centered in the squares. This means that they would not have a corresponding pixel value in the original image.

![](https://kevinzakka.github.io/assets/stn/stickman.png) 

So for example, suppose that after rotating an image, we need to find the pixel value at the location ***(6.7, 3.2)***. The problem with this is that there is no such thing as fractional pixel locations.

**bilinear interpolation**

![](https://kevinzakka.github.io/assets/stn/interpol.png) 


![](https://github.com/xuuuuuuchen/xuuuuuuchen.github.io/blob/master/img/2018-07-26-readnote/1.png?raw=true) 

## Digitally Reconstructed Radiograph (DRR)

![](https://media.springernature.com/lw785/springer-static/image/art%3A10.1186%2Fs12938-017-0353-8/MediaObjects/12938_2017_353_Fig1_HTML.gif) 

![](https://image.slidesharecdn.com/presentation-100511175011-phpapp02/95/generation-of-planar-radiographs-from-3d-anatomical-models-using-the-gpu-3-728.jpg?cb=1273601116) 

![](https://image.slidesharecdn.com/presentation-100714114159-phpapp01/95/generation-of-planar-radiographs-from-3d-anatomical-models-using-the-gpu-6-728.jpg?cb=1279107927) 


