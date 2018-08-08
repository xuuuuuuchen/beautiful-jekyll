---
layout: post
published: Ture
category: "Literature Review of X-ray Landmark Detection"
title: Literature Review of X-ray Landmark Detection
image: http://www-o.ntust.edu.tw/~cweiwang/celph/images/output.gif
tags: [Literature Review, X-ray, Landmark, Detection]
---




## Motivation

In clinical practice, manual marking is required (usually trace out craniofacial structure contours on X-ray images first, and then extract landmarks from linear and angular reference lines and other geometrical shapes.) 

---> However, manual marking is time-consuming and subjective, and this tends to suffer from intra- and inter-observer errors. 

---> In order to deal with issues of manual marking, many clinical research studies focused on landmark identification problems.

---> However, auto-identification of anatomical landmarks is difficult and poorly explored due to the complexity and variability of X-ray images.

---> include (1) variations on individual structures, (2) image blurs caused by device-specific projection magnifications, (3) and image complexity due to the overlapping contralateral structures.







## Background

................................................................................

- Automatic Localization/Identification of **cephalometric** landmarks

................................................................................

In 2006, a modified active shape model to detect 12 anatomical landmarks, achieving a 71% success rate of landmark detection within 2.0 mm and 88% within 4.0 mm. 

>W. Yue, D. Yin, C. Li, G. Wang, and T. Xu, “Automated 2-D cephalo- metric analysis on x-ray images by a model-based approach,” IEEE Trans. Biomed. Eng., vol. 53, no. 8, pp. 1615– 1623, Aug. 2006

................................................................................

In 2009, combined **neural networks with modified active shape models** and developed a techniquewith 93% landmark detection accuracy for bony structures within 5.0 mm.

>R. Kafieh, S. Sadri, A. Mehri, and H. Raji, “Discrimination of bony structures in cephalograms for automatic landmark detection,” Commun. Comput. Inf. Sci., vol. 6, no. 1, pp. 609–620, 2009.

................................................................................

In 2013, an automatic cephalometric landmark detection method, which uses **Zernike moment-based features** for initial landmark estimation and computes small expectation window, and resulted in a mean error of 1.84 mm and standard deviation is 1.24 for 18 observed landmarks. However, variations in image data (**e.g.** image quality, imaging radiation time, subject age and gender) and evaluation approaches (e.g. the size of the manually obtained ground truth data from one pixel to a square region) greatly influence the evaluation outcome.

>A. Kaur and C. Singh, “Automatic cephalometric landmark detection using zernike moments and template matching,” Signal, Image Video Process., vol. 9, no. 1, pp. 117–132, 2015.

................................................................................


In 2014, developed a framework that describes the intensity appearance of each landmark by **Haar-like features** and applies the **theory of random forests (RFs)** to combine these features into a landmark candidate point detector. 

![](https://github.com/xuuuuuuchen/xuuuuuuchen.github.io/blob/master/img/2018-08-07-readnote/5.png?raw=true) 

manually placed 44 additional auxiliary [ɔːɡˈzɪljərɪ] landmarks at visually distinctive locations such as the nose tip and corners of cervical vertebrae.

>B. Ibragimov, B. Likar, F. Pernuš, and T. Vrtovec, “Automatic cephalometric X-ray landmark detection by applying game theory and random forests,” in Proc. ISBI Int. Symp. Biomed. Imag. 2014, Au- tomat. Cephalometric X-Ray Landmark Detection Challenge, Beijing, China, 2014, pp. 1–8

................................................................................


In 2014, built a fully automatic algorithm for landmark detection on 2D cephalometric X-ray images using RF regression.
includes two phases: (1) landmark detection phase and (2) landmark modification phase.

![](https://github.com/xuuuuuuchen/xuuuuuuchen.github.io/blob/master/img/2018-08-07-readnote/1.png?raw=true) 

To modify landmark positions, which are not correctly detected, a **sparse shape composition model** is built. 

The landmark detection phase can be further divided into two steps: 

**a)** RF-based landmark detector training step + **b)** landmark prediction step. 

RF-based landmark detector training is performed only once on 100 training images and is independent from any test image. it trains a separate RF-based landmark detector for each landmark, and therefore they obtain 19 detectors for all landmark positions. 


>C. Chu, C. Chen, L.-P. Nolte, and G. Zheng, “Fully automatic cephalo- metric x-ray landmark detection using random forest regression and sparse shape composition,” in Proc. ISBI Int. Symp. Biomed. Imag. 2014, Automat. Cephalometric X-Ray LandmarkDetection Challenge, Beijing, China, 2014, pp. 9–16

................................................................................


![](https://github.com/xuuuuuuchen/xuuuuuuchen.github.io/blob/master/img/2018-08-07-readnote/3.png?raw=true) 


In 2014, The overview of Chen and Zheng's landmark detection framework is given in Fig. 6. 

In the **training step**, Chen and Zheng **randomly sample a set of square image patches around the ground-truth landmark location**. The visual features and displacements to the landmark of these patches comprise the training data. 

Then, given a new image, they randomly sample a set ofimage patches and calculate their features. To estimate the displacement (取代，位移；) of each patch, they take a data-driven approach by defining an objective function on the displacements to enforce the following constraints: 

1. Patches with similar features should have similar displacements. 

2. The displacements of test patches should be consistent with the triangle structure (i.e. the difference between displacements from the respective centers of two patches to the landmark should be close to the coordinate difference of the two patch centers). 

In this way, each patch makes a vote on the landmark position. Chen and Zheng treat each vote as a small Gaussian distribution and aggregate them into a probability map, the mode of which is returned as the detected landmark location. 

>C. Chen and G. Zheng, “Fully-automatic landmark detection in cephalometric x-ray images by data-driven image displacement es- timation,” in Proc. ISBI Int. Symp. Biomed. Imag. 2014, Automat. Cephalometric X-Ray Landmark Detection Challenge, Beijing, China, 2014, pp. 17–24.

................................................................................


In 2014, A machine learning tree based approach (Belgium) has two stages: a training and a testing stage. 

In the training stage, they extract the **aforementioned features** from a set of windows centered around the position of landmarks as **true positive** TP samples, and a set of randomly selected windows not near the position of landmarks as **true negative** TN samples. These positive and negative samples are used to train a RF classifier with 22 trees of depth 10. 

For a new image, Mirzaalian and Hamarneh apply the pictorial (形象化) structure algorithm to globally optimize the cost function in **(5)**. Note that the pictorial structure requires computing the first term over an acyclic graph (tree) to connect landmarks. The problem can be solved by applying the **minimum spanning tree** 最小生成树 over a complete graph with the 19 landmarks as vertices andwith edge weights set as the covariance values of the edges [38].

cost function is:

![](https://github.com/xuuuuuuchen/xuuuuuuchen.github.io/blob/master/img/2018-08-07-readnote/6.png?raw=true) 

![](https://github.com/xuuuuuuchen/xuuuuuuchen.github.io/blob/master/img/2018-08-07-readnote/4.png?raw=true) 


>H. Mirzaalian and G. Hamarneh, “Automatic globally-optimal pic- torial structures with random decision forest based likelihoods for cephalometric x-ray landmark detection,” in Proc. ISBI Int. Symp. Biomed. Imag. 2014, Automat. Cephalometric X-Ray Landmark Detection Challenge, Beijing, China, 2014, pp. 25–36.

................................................................................



In 2014, Vandaele et al. address the problem as **19 separate binary pixel classification problems**, one for each landmark. One pixel belongs to the positive class if its distance to the landmark position is less than R, where R
is a method parameter. 

Otherwise, it belongs to the negative class. A (x,y) pixel is described by raw pixel values in 16*16 windows centered at translated positions (x + t_x, y + t_y) and extracted at six different resolutions. Parameters t_x and t_y allow to detect the landmark based on a structure which is not centered at the pixel. 

they use **extremely randomized trees** (绝对随机森林) as the pixel classifier. Training pixels are randomly extracted in a radius of at most 4 cm to the landmark. The median position of pixels classified as positive with the highest confidence are then returned as the final landmark position. All method parameters are tuned via a 10-fold cross-validation.


>R. Vandaele, R. Marée, S. Jodogne, and P. Geurts, “Automatic cephalometric x-ray landmark detection challenge 2014: A tree-based approach,” in Proc. ISBI Int. Symp. Biomed. Imag. 2014, Automat. Cephalometric X-Ray Landmark Detection Challenge, Beijing, China, 2014, pp. 37–44.
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          
![](https://github.com/xuuuuuuchen/xuuuuuuchen.github.io/blob/master/img/2018-08-07-readnote/7.png?raw=true) 

![](https://github.com/xuuuuuuchen/xuuuuuuchen.github.io/blob/master/img/2018-08-07-readnote/8.png?raw=true) 

![](https://github.com/xuuuuuuchen/xuuuuuuchen.github.io/blob/master/img/2018-08-07-readnote/9.png?raw=true) 

................................................................................

## Previous Methods


## Evaluation Methods

![](https://github.com/xuuuuuuchen/xuuuuuuchen.github.io/blob/master/img/2018-08-07-readnote/2.png?raw=true) 
