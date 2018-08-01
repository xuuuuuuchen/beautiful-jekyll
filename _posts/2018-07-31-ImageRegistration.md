---
layout: post
published: Ture
category: "Image Registration"
title: Literature Review of Image Registration
image: https://i.stack.imgur.com/vipHn.jpg

tags: [Literature Review, Image Registration]
---

![](https://i.stack.imgur.com/vipHn.jpg) 

## Image Registration Background

One of the images is referred to as the **moving** or **source** images.
The others are referred to as the **target**, **fixed** or **sensed** images.

Image registration can be classified into intensity-based and feature-based.
>A. Ardeshir Goshtasby: 2-D and 3-D Image Registration for Medical, Remote Sensing, and Industrial Applications, Wiley Press, 2005.

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

## Previous Methods in Medical Image Registration

>G. Wu et al.. "Scalable high-performance image registration framework by unsupervised deep feature representations learning." IEEE Transactions on Biomedical Engineering 2016
[[Reading Note]](https://xuuuuuuchen.github.io/2018-07-31-readnote/)


Contributions:
Comment: "used a convolutional stacked auto-encoder (**CAE**) to extract features from fixed and moving images that are subsequently used in conventional deformable image registration algorithms. However, the CAE is decoupled from the image registration task and hence, it does not necessarily extract the features most descriptive for image registration. The training of the CAE was unsupervised, but the registration task was not learned end-to-end."


> Miao et al. A CNN regression approach for real-time 2D/3D registration. IEEE transactions on medical imaging. 2016 [[Reading Note]](https://xuuuuuuchen.github.io/2018-07-23-readnote-add/)

Contributions:
Comment:" used a convolutional neural network (ConvNet) regressor to predict a transformation matrix for rigid registration of synthetic 2D to 3D images. "


> Liao, Rui, et al. "An Artificial Agent for Robust Image Registration." AAAI. 2017. [[NEED A Reading Note]](https://xuuuuuuchen.github.io/2018-08-01-readnote-add/) 

Contributions:
Comment:" used a ConvNet for intrapatient rigid registration of CT to cone-beam CT applied to either cardiac or abdominal images. "

"Both registration methods (Miao et al. and Liao et al.) were supervised: for training, transformation parameters were generated, which is task specific and highly challenging."



> Jaderberg, Max, Karen Simonyan, and Andrew Zisserman. "Spatial transformer networks." Advances in neural information processing systems. 2015. [[Reading Note]](https://xuuuuuuchen.github.io/2018-07-26-readnote/) [[Paper]](https://arxiv.org/abs/1506.02025)  *(‎Cited by 901)*: " 

Contributions:
Comment:" introduced the spatial transformer network (STN) that can be used as a building block that aligns input images in a larger network that performs a particular task. By training the entire network end-to-end, the embedded STN deduces optimal alignment for solving that specific task. "
"However, alignment is not guaranteed, and it is only performed when required for the task of the entire network. The STNs were used for affine transformations, as well as deformable transformations using thin-plate splines. However, an STN needs many labeled training examples, and to the best of our knowledge, have not yet been used in medical imaging."

Comment:" The focus of STN was not an accurate alignment of two images, but a rough transformation of a single input image to a canonical form, for the purpose of improved classification accuracy. More- over its application has been demonstrated only on 2-D im- ages, not 3-D volumes."

Spatial Transformer Networks (STN) **Applications**

> Yoo, Inwan, et al. "ssEMnet: Serial-section Electron Microscopy Image Registration using a Spatial Transformer Network with Learned Features." Deep Learning in Medical Image Analysis and Multimodal Learning for Clinical Decision Support. Springer, Cham, 2017. 249-257. [[Reading Note]](https://xuuuuuuchen.github.io/2018-07-30-readnote/)

Contributions:
Comment:" 


> Li H, Fan Y. Non-rigid image registration using fully convolutional networks with deep self-supervision. arXiv preprint arXiv:1709.00799. 2017 Sep 4. [[NEED A Reading Note]](https://xuuuuuuchen.github.io/2018-08-01-readnote-add-add/)

Contributions:
Comment:" 


a recurrent neural network (RNN) + STN

> Li H, Fan Y. Non-rigid image registration using fully convolutional networks with deep self-supervision. arXiv preprint arXiv:1709.00799. 2017 Sep 4. [[NEED A Reading Note]](https://xuuuuuuchen.github.io/2018-08-01-readnote-add-add-add/)

Contributions:
Comment:" 

> Lin, Chen-Hsuan, and Simon Lucey. "Inverse compositional spatial transformer networks." arXiv preprint arXiv:1612.03897 (2016). [[NEED A Reading Note]](https://xuuuuuuchen.github.io/2018-08-02-readnote/)

Contributions:
Comment:" 





