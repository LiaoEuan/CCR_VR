# PID-Inspired Continuous Correction for Visual Reprogramming

This repository is the official PyTorch implementation of the **ICML2025** paper:
[PID-Inspired Continuous Correction for Visual Reprogramming],
authored by Anonymous Authors.

**Key Words:**
Visual Reprogramming, Closed-loop Correction Reprogramming (CCR), PID, Proportional Adjustment Controller (PAC), Fine-grained, Machine Learnin

**Abstract:**
Visual Reprogramming (VR) adapts pre-trained models to new tasks through pixel-level attention modulation without parameter modification. While existing methods achieve competent performance on basic classification, they dispersed attention in critical discriminative regions for fine-grained tasks. Inspired by PID control theory, we propose Closed-loop Correction Reprogramming (CCR) that integrates proportional feedback. Concretely, the framework comprises dual streams: a Foundation Flow for initial attention patterns and a Correction Flow that iteratively refines them with residual feedback, alternating between both. A Proportional Adjustment Controller (PAC) dynamically calibrates perturbation intensity via learnable error mapping--enhancing the correction flow's contribution in response to increased foundational stream errors, otherwise maintaining the foundation's dependable attributes. Experiments on 11 benchmarks demonstrate CCR achieves up to 10.8% accuracy gain with only 0.64% parameter increase, attaining 8.62% average improvement on five challenging fine-grained datasets (GTSRB, FLOWERS102, DTD, UCF101, FOOD101). The framework offers enhanced visual cues that improve discrimination in fine-grained classification.

**Method:**
Current visual reprogramming algorithms often encounter the ”fog effect” in handling downstream fine-grained tasks, where the model struggles to clearly identify the key detailed features of objects. This blurring phenomenon significantly affects the model’s performance in fine-grained classification. To address this issue, we propose Closed-loop Correction Reprogramming, which combines the closed-loop feedback mechanism and proportional control principles from classical control theory.



## Dataset
- For CIFAR10, CIFAR100, GTSRB, SVHN, simply run our code and use [TorchVision](https://pytorch.org/vision/0.15/datasets.html) to download them automatically.
- For other datasets, follow [this paper](https://github.com/OPTML-Group/ILM-VP) to prepare them.

Put all the download datasets in `/dataset/`

## Environment

- Python (3.10.0)
- PyTorch (2.0.1) 
- TorchVision (0.15.2)
        
        pip install -r requirements.txt
  
## Training

- For ViT-based pretrained model

        python instancewise_vp.py --dataset cifar10 --network ViT_B32 --seed 0

## Acknowledgements

This repo is built upon these previous works:

- [lukemelas/PyTorch-Pretrained-ViT](https://github.com/lukemelas/PyTorch-Pretrained-ViT)
- [OPTML-Group/ILM-VP](https://github.com/OPTML-Group/ILM-VP)
- [SMM](https://github.com/tmlr-group/SMM/tree/main)
