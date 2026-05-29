<div align="center">

# SnowLab2VISPA

[![NeurIPS 2024](https://img.shields.io/badge/NeurIPS-2024-blue.svg)](https://proceedings.neurips.cc/paper_files/paper/2024)
[![Official Repo](https://img.shields.io/badge/Official-Repo-green.svg)](https://github.com/snownus/bnn_vi)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)


**Code Integration of the NeurIPS 2024 Paper**

*Training Binary Neural Networks via Gaussian Variational Inference and Low-Rank Semidefinite Programming*

</div>

## ⚠️ Important: Official Implementation

**This repository is a reorganized version integrated into my personal codebase.**

The **official and authoritative implementation** of the paper is maintained at:

> 👉 **[https://github.com/snownus/bnn_vi](https://github.com/snownus/bnn_vi)**

Please refer to that repository for the canonical code, updates, and the most complete reproduction pipeline. This repo is provided as a convenience for those following my code structure, but users should default to the official implementation for reproducing results or extending the method.

## ❄️ About Me & This Repo

I am a **co-author** of the paper. This repository reorganizes the method's core components to align with my broader research codebase (`SnowLab2` ecosystem) for consistency and maintainability. The algorithmic logic is identical to the official version; changes are limited to code organization, configuration interfaces, and documentation style.

## 📌 Overview

**SnowLab2VISPA** (Variational Inference with Semidefinite Programming for Activation) introduces a fundamentally new approach to training Binary Neural Networks (BNNs). Conventional BNN training relies on heuristic gradient estimators like the Straight-Through Estimator (STE). This work instead formulates BNN training as **Gaussian Variational Inference (VI)** and solves the resulting combinatorial optimization subproblems exactly using a **low-rank Semidefinite Programming (SDP)** relaxation.

Key advantages:
- **Principled Optimization:** No biased gradient approximations through discrete activations.
- **State-of-the-Art Accuracy:** Competitive or superior results compared to STE-based BNNs.
- **Theoretical Guarantees:** Probabilistic interpretation with formal convergence properties.

## 🖥️ Experiments

This benchmark supports two main experimental tracks:

### 🧩 Experiments on CIFAR and Tiny-imagenet

We evaluate ProbBop on CIFAR-10, cifar100 and Tiny-ImageNet under two binarization settings.

#### 📊 Weight Binarization Only

| Architecture | CIFAR-10 | CIFAR-100 | Tiny-ImageNet |
|-----------|:--------:|:---------:|:-------------:|
| VGG16 | ⌛️ | ⌛️ | ⌛️ |
| ResNet18 | ⌛️ | ⌛️ | ⌛️ |

#### 📊 Full Binarization (Weights + Activations)

| Architecture | CIFAR-10 | CIFAR-100 | Tiny-ImageNet |
|-----------|:--------:|:---------:|:-------------:|
| VGG_Small | ⌛️ | ⌛️ | ⌛️ |
| ResNet18 | ⌛️ | ⌛️ | ⌛️ |

<details> <summary>🔁 All Reproducible Commands on ResNet</summary>

---

**CIFAR-10 with SGD** 
```bash
python main_binary_sgdat.py --model resnet_binary --save resnet_binary_cifar10_SGD --dataset cifar10 --bin_regime "{0: {'optimizer': 'SGD','lr':1e-4}}" --binarization det --input_size 32 --epochs 200 -b 256 --gpus 0
```

</details>


## 🎨 Experiments on ImageNet

The results will coming soon~


## 📝 Citation

If you use this code or build upon our method, please cite our paper:

```bibtex
@article{orecchia2024training,
  title={Training binary neural networks via gaussian variational inference and low-rank semidefinite programming},
  author={Orecchia, Lorenzo and Hu, Jiawei and He, Xue and Wang, Zhe and Yang, Xulei and Wu, Min and Geng, Xue},
  journal={Advances in Neural Information Processing Systems},
  volume={37},
  pages={63963--63985},
  year={2024}
}
