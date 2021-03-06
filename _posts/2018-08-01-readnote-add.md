---
layout: post
published: Ture
category: "Image Registration"
title: Rui Liao 2017 (04 Aug 2018 Reading Notes II)
subtitle: An Artificial Agent for Robust Image Registration
image: https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRh8NfGi3CKsuqXB2ty8iPXT6uekPX8uR09rt1oROev74uslRy6
tags: [Literature Review, Image Registration]
---

![](https://www.wikihow.com/images/9/99/Do-a-Literature-Review-Step-13-Version-2.jpg) 

**Title:** An Artificial Agent for Robust Image Registration (Thirty-First AAAI Conference on Artificial Intelligence (AAAI-17)) [Paper Link](https://arxiv.org/abs/1611.10336)

**Authors:** Rui Liao, Shun Miao, Pierre de Tournemire, Sasa Grbic, Ali Kamen, Tommaso Mansi, Dorin Comaniciu

**Association:** Technology Center, Medical Imaging Technologies Siemens Medical Solutions USA

**Submission:** 2017


.................................................................................................................................

## >>> Background of Deep Learning in Medical Image Analysis

[[NEED A Reading Notes]](https://xuuuuuuchen.github.io/2018-08-01-DeepLearninginMedicalImageAnalysis/)

## >>> A Review: Robot-Assisted Endovascular Catheterization Technologies: 

[[NEED A Reading Notes]](https://xuuuuuuchen.github.io/Robot-AssistedEndovascularCatheterizationTechnologies/)

.................................................................................................................................
## >>> Image Registration Basic Knowledge

[[Basic Knowledge]](https://xuuuuuuchen.github.io/2018-07-31-ImageRegistration-basic/)

## >>> Image Registration Literature Review

[[Literature Review]](https://xuuuuuuchen.github.io/2018-07-31-ImageRegistration/)

## >>> Slice-To-Volume Medical Image Registration Background

[[NEED A Reading Notes]](https://xuuuuuuchen.github.io/2018-08-01-ImageRegistration-2D-3D/)

.................................................................................................................................

## Motivation


## Contributions

**(0)** decompose the registration task into a se- quence of (often easier) classification problems, i.e. find- ing the best action among a limited set of possible solutions to improve the alignment. Repeating this process can result in a converging solution. 

**(1)** We train the intelligent agent in a greedy supervised fashion, which is a magni- tude more efficient with only a small fraction of the mem- ory footprint than in standard DRL setup, where the agent learns through repeated trial and errors (Mnih et al. 2015; Silver et al. 2016); 3)

**(2)** propose an effective data aug- mentation and sampling strategy so that the agent could be trained robustly using only a small number of labelled train- ing pairs available from patients;

**(3)** For a combined robust- ness and accuracy, we propose a hierarchical registration framework relying on the trained networks from the coarse image layer to register successively the more refined (higher- resolution) image layers


## Methods

![](https://github.com/xuuuuuuchen/xuuuuuuchen.github.io/blob/master/img/2018-08-12-readnote/8.jpg?raw=true) 

![](https://github.com/xuuuuuuchen/xuuuuuuchen.github.io/blob/master/img/2018-08-12-readnote/9.jpg?raw=true) 

![](https://github.com/xuuuuuuchen/xuuuuuuchen.github.io/blob/master/img/2018-08-12-readnote/10.jpg?raw=true) 

![](https://github.com/xuuuuuuchen/xuuuuuuchen.github.io/blob/master/img/2018-08-12-readnote/11.jpg?raw=true) 

![](https://github.com/xuuuuuuchen/xuuuuuuchen.github.io/blob/master/img/2018-08-12-readnote/12.jpg?raw=true) 


