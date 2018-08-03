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

- automatic localization/identifica- tion of **cephalometric** landmarks

In 2006, a modified active shape model to detect 12 anatomical landmarks, achieving a 71% success rate of landmark de- tection within 2.0 mm and 88% within 4.0 mm. 

>W. Yue, D. Yin, C. Li, G. Wang, and T. Xu, “Automated 2-D cephalo- metric analysis on x-ray images by a model-based approach,” IEEE Trans. Biomed. Eng., vol. 53, no. 8, pp. 1615– 1623, Aug. 2006

In 2009, combined neural networks with modified active shape models and developed a techniquewith 93% landmark detection accuracy for bony structures within 5.0 mm.

>R. Kafieh, S. Sadri, A. Mehri, and H. Raji, “Discrimination of bony structures in cephalograms for automatic landmark detection,” Commun. Comput. Inf. Sci., vol. 6, no. 1, pp. 609–620, 2009.

In 2013, an automatic cephalometric landmark detection method, which uses Zernike moment-based features for initial landmark estimation and computes small expectation window, and resulted in a mean error of 1.84 mm and standard deviation is 1.24 for 18 observed landmarks. However, variations in image data (e.g. image quality, imaging radiation time, subject age and gender) and evaluation approaches (e.g. the size of the manually obtained ground truth data from one pixel to a square region) greatly influence the evaluation outcome.

>A. Kaur and C. Singh, “Automatic cephalometric landmark detection using zernike moments and template matching,” Signal, Image Video Process., vol. 9, no. 1, pp. 117–132, 2015.


In 2014, developed a framework that describes the intensity appearance of each landmark by **Haar-like features** and applies the **theory of random forests (RFs)** to combine these features into a landmark candidate point detector. 

![](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTNFzKcU3s5bJKxmagKXIqBpIQYLDtEuibaoBaR48dm3Yvahp1y) 

manually placed 44 additional auxiliary landmarks at visually distinctive locations such as the nose tip and corners of cervical vertebrae.

>B. Ibragimov, B. Likar, F. Pernuš, and T. Vrtovec, “Automatic cephalometric X-ray landmark detection by applying game theory and random forests,” in Proc. ISBI Int. Symp. Biomed. Imag. 2014, Au- tomat. Cephalometric X-Ray Landmark Detection Challenge, Beijing, China, 2014, pp. 1–8

In 2014, built a fully automatic algorithm for landmark detection on 2D cephalometric X-ray images using RF regression.
includes two phases: (1) landmark detection phase and (2) landmark modification phase.

![](https://github.com/xuuuuuuchen/xuuuuuuchen.github.io/blob/master/img/2018-08-07-readnote/1.png?raw=true) 

To modify landmark positions, which are not correctly detected, a **sparse shape composition model** is built. The landmark detection phase can be further divided into two steps: **a)** RF-based landmark detector training step, **b)** landmark prediction step. RF-based landmark detector training is performed only once on 100 training images and is independent from any test image. it trains a separate RF-based landmark detector for each landmark, and therefore they obtain 19 detectors for all landmark positions. Given


>C. Chu, C. Chen, L.-P. Nolte, and G. Zheng, “Fully automatic cephalo- metric x-ray landmark detection using random forest regression and sparse shape composition,” in Proc. ISBI Int. Symp. Biomed. Imag. 2014, Automat. Cephalometric X-Ray LandmarkDetection Challenge, Beijing, China, 2014, pp. 9–16

![](https://github.com/xuuuuuuchen/xuuuuuuchen.github.io/blob/master/img/2018-08-07-readnote/3.png?raw=true) 

In 2014, Fully-automatic landmark detection in cephalometric X-ray images by data-driven image displacement estimation (Switzerland). 

>C. Chen and G. Zheng, “Fully-automatic landmark detection in cephalometric x-ray images by data-driven image displacement es- timation,” in Proc. ISBI Int. Symp. Biomed. Imag. 2014, Automat. Cephalometric X-Ray Landmark Detection Challenge, Beijing, China, 2014, pp. 17–24.

![](https://github.com/xuuuuuuchen/xuuuuuuchen.github.io/blob/master/img/2018-08-07-readnote/4.png?raw=true) 

In 2014, randomly sample a set of square image patches around the ground-truth landmark location.

>H. Mirzaalian and G. Hamarneh, “Automatic globally-optimal pic- torial structures with random decision forest based likelihoods for cephalometric x-ray landmark detection,” in Proc. ISBI Int. Symp. Biomed. Imag. 2014, Automat. Cephalometric X-Ray Landmark Detection Challenge, Beijing, China, 2014, pp. 25–36.

In 2014, A machine learning tree-based ap- proach (Belgium).

>R. Vandaele, R. Marée, S. Jodogne, and P. Geurts, “Automatic cephalometric x-ray landmark detection challenge 2014: A tree-based approach,” in Proc. ISBI Int. Symp. Biomed. Imag. 2014, Automat. Cephalometric X-Ray Landmark Detection Challenge, Beijing, China, 2014, pp. 37–44.






- Intensity-based feature selection methods

Intensity-based methods compare intensity patterns in images via correlation metrics
However, two image patches that show similar, or even the same, distribution of intensity values do not guarantee the two points are corresponded from an anatomical (解剖学的; 结构上的) point of view

>V. Arsigny et al., “A log-Euclidean framework for statistics on diffeo- morphisms,” in Proc. Med. Image Comput. Comput.-Assisted Intervention Conf., 2006, pp. 924–931.

>J. Ashburner, “A fast diffeomorphic image registration algorithm,” Neu- roImage, vol. 38, pp. 95–113, 2007.

>B. Avants et al., “Symmetric diffeomorphic image registration: Eval- uating automated labeling of elderly and neurodegenerative cortex and frontal lobe,” in Proc. Int. Workshop Biomed. Image Registration, 2006, pp. 50–57.

>D. Rueckert et al., “Nonrigid registration using free-form deforma- tions: Application to breast MR images,” IEEE Trans. Med. Imag., vol. 18, no. 8, pp. 712–721, Aug. 1999.

>T. Vercauteren et al., “Diffeomorphic demons: Efficient non-parametric image registration,” NeuroImage, vol. 45, pp. S61–S72, 2009.

- Feature-based feature selection methods

feature-based methods find correspondence between image features such as points, lines, and contours.

Handcrafted features, such as geometric moment invariants:
>D. Shen and C. Davatzikos, “HAMMER: Hierarchical attribute matching mechanism for elastic registration,” IEEE Trans.Med.Imag., vol. 21, no. 11, pp. 1421–1439, Nov. 2002.

Gabor filter:
>Y. Zhan and D. Shen, “Deformable segmentation of 3-D ultrasound prostate images using statistical texture matching method,” IEEE Trans. Image Process., vol. 25, no. 3, pp. 256–272, Mar. 2006.

Others:
>Q. Wang et al., “Attribute vector guided groupwise registration,” Neu- roImage, vol. 50, pp. 1485–1496, 2010.

>G. Wu et al., “S-HAMMER: Hierarchical attribute-guided, symmetric diffeomorphic registration for MR brain images,” Human Brain Mapping, vol. 35, pp. 1044–1060, 2013

>G. Wu et al., “TPS-HAMMER: Improving HAMMER registration al- gorithm by soft correspondence matching and Thin-plate splines based deformation interpolation,” NeuroImage, vol. 49, pp. 2225–2233, 2010.

>G. Wu et al., “Feature-based groupwise registration by hierarchical anatomical correspondence detection,” Human Brain Mapping, vol. 33, pp. 253–271, 2012.

- Supervised learning-based methods:

"have been proposed to select the best set of features from a large feature pool that may include plenty of redundant handcrafted features. However, for this approach, the ground-truth data with known correspondences across the set of training images is required. Because human experts are typically needed to generate ground- truth data, it is well known that obtaining this type of data can be a very laborious and subjective process. In many cases, ground- truth data are simply not available, and even if it does exist, the size of the training population may be very small, which may dramatically affect the accuracy of the registration method. In general, image registration methods that use supervised learning for feature selection."

>R. W. K. So and A. C. S. Chung, “Learning-based non-rigid image regis- tration using prior joint intensity distributions with graph-cuts,” presented at the 18th Int. Conf. Image Process., Brussels, Belgium, 2011.

>Y. Ou et al., “DRAMMS: Deformable registration via attribute matching and Mutual-saliency weighting,” Med. Image Anal., vol. 15, pp. 622–639, 2011.

>D. Lee et al., “Learning similarity measure for multi-modal 3D image registration,” presented at the IEEE Conf. Comput. Vision Pattern Recog., Maimi, FL, USA, 2009.

>J. Jiang et al., “Learning based coarse-to-fine image registration,” pre- sented at the IEEE Conf. Comput. Vision Pattern Recog., Anchorage, AK, USA, 2008.

>G. Wu et al., “Learning best features and deformation statistics for hi- erarchical registration of MR brain images,” Inf. Process. Med. Imag., vol. 20, pp. 160–171, 2007.

- unsupervised learning-based feature selection methods:

To overcome the limitations mentioned above, unsupervised learning-based feature selection methods require further investigation. Because of the complexity of the data, conventional unsupervised approaches that use 

ISOMAP 
> J. B. Tenenbaum et al., “ A global geometric framework for nonlinear dimensionality reduction,” Science, vol. 290, pp. 640–646, 2000.
kernel SVM 
>H. Larochelle et al., “An empirical evaluation of deep architectures on problems with many factors of variation,” presented at the 24th Int. Conf. Mach. Learning, Corvalis, OR, USA, 2007

However, since the learned features are found using only a single layer, or a **shallow model**, the selected features may lack high-level perception knowledge (e.g., shape and context information) and may not be suitable for correspondence detection.

The general concept behind deep learning is to learn hierarchical feature representations by inferring simple representations first and then pro- gressively build up more complex ones from the previous level. Compared with the shallow models, a deep learning architecture can encode multilevel information from simple to complex.

**Why Deep Learning**

for image registration, deep learning is very promising because
1) is an unsupervised learning approach that does not require ground truth
2) uses a hierarchical deep architec- ture to infer complex nonlinear relationships
3) is completely data driven and not based on handcrafted feature selection
4) can quickly and efficiently compute the hierarchical feature representation for any image patch in the testing data given the trained hierarchical deep architecture (or network).


- unsupervised deep learning-based fmethods:

>G. Wu et al., “Unsupervised deep feature learning for deformable image registration of MR brains,” presented at the 16th Int. Conf. Med. Imag. Comput. Comput. Assisted Intervention, Nagoya, Japan, 2013.

## Previous Methods

>G. Wu et al.. "Scalable high-performance image registration framework by unsupervised deep feature representations learning." IEEE Transactions on Biomedical Engineering 2016
[[Reading Note]](https://xuuuuuuchen.github.io/2018-07-31-readnote/)


## Evaluation Methods

![](https://github.com/xuuuuuuchen/xuuuuuuchen.github.io/blob/master/img/2018-08-07-readnote/2.png?raw=true) 
