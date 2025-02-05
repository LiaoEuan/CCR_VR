# PID-Inspired Continuous Correction for Visual Reprogramming

This repository is the official PyTorch implementation of the **ICML2025** paper:
[Sample-specific Masks for Visual Reprogramming-based Prompting],
authored by Anonymous Authors.

**Key Words:**
Visual Reprogramming, Closed-loop Correction Reprogramming (CCR), PID, Proportional Adjustment Controller (PAC), Fine-grained, Machine Learnin

**Abstract:**
*Visual reprogramming* (VR) is a prompting technique that aims to re-purpose a pre-trained model (e.g., a classifier on ImageNet) to target tasks (e.g., medical data prediction) by learning a *small-scale pattern* added into input images instead of tuning considerable parameters within the model. 
The location of the pattern within input samples is usually determined by a pre-defined mask *shared across all samples*. 
In this paper, we show that the shared mask potentially limits VR's generalization and increases its approximation error due to the lack of sample-level adaptation.
Motivated by this finding, we design a new framework for VR called *sample-specific multi-channel masks* (SMM). 
Specifically, SMM employs a lightweight ConvNet and patch-wise interpolation to generate sample-specific three-channel masks instead of a shared and pre-defined mask.
Since we generate different masks for individual samples, SMM is theoretically shown to reduce approximation error for the target tasks compared with existing state-of-the-art VR methods. We also empirically demonstrate its performance gain on both ResNet and ViT.
The success of SMM further highlights the broader applicability of VR in leveraging the latent knowledge of pre-trained models for various target tasks.

**Method:**
Comparison between existing methods (a) and our method (b). 
Previous padding-based reprogramming adds zeros around the target image, while resizing-based reprogramming adjusts image dimensions to fit the required input size. 
Both methods use a pre-determined *shared* mask to indicate the valid location of pattern $\delta$. Our method, on the other hand, takes a more dynamic and tailored approach. 
We resize each target image and apply a different three-channel mask accordingly, driven by a lightweight model $f_{\rm mask}$ and an interpolation up-scaling module, allowing for more variability in individual samples.
