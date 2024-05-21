# README

This repo contains the code from the medium post: [Understanding and Coding DETR](https://medium.com/@rafaeltol/understanding-and-coding-detr-detection-transfomer-80e4c206fbc8?source=friends_link&sk=f477a7a5b7526cab99e66b4798e960f3).

Reproduce the notebook `detr.ipynb` on Colab [![](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1-TVkq7PrXnlu1IObXjhnT1h6HKzbq2eI?usp=sharing).


## Download my training checkpoints

| | | | |
|---|---|---|---|
|coco-tiny | 40k iterations | [ckpt](https://drive.google.com/file/d/1FOx7sTVd0XNrPta-A3F_l_c_7U1z4moQ/view?usp=sharing) | [loss-history](https://drive.google.com/file/d/1QFD87x-ffAufRnse1wiwlWEk53wvolgx/view?usp=sharing) |
|coco-complete | 150 epochs | [ckpt](https://drive.google.com/file/d/1r48PzfFaOUtyKACO31-koT8LPVZKQG0t/view?usp=sharing) | [loss-history](https://drive.google.com/file/d/14s0H4_95VaZvxndxjRQFd0S3oKJJydRf/view?usp=sharing) |


## Introduction

AI is on fire these days, and transformer-based architectures are one of the key factors that leveraged the last AI success cases. In the computer vision field, **DEtection TRansformer (DETR)** from Carion et al. (2020) was one of the first works to demonstrate that transformers could also be used for vision tasks, reaching competitive results with other baseline works.

Another meaningful DETR contribution was the introduction of a new solution paradigm for the object detection task that handles it as a set prediction problem. The new paradigm introduced a new element called object queries and freed the object detection solutions of hand-designed mechanisms like anchors or non-maximum suppression (NMS). This paradigm was later applied to segmentation tasks and state-of-the-art models like Mask2Former (Cheng et al., 2022) and OneFormer (Jain et al., 2023).

This article will expose the main mechanisms of the DETR implementation, and, in the end, you'll be able to train the network on the COCO dataset without any external scripts but PyTorch methods.
