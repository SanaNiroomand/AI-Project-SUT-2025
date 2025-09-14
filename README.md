# 🚀 Phase 1: Image Segmentation Project

## Overview

This phase focuses on **semantic image segmentation** for road detection using advanced U-Net-based architectures. We implement three models from scratch using **PyTorch**: **U-Net**, **Attention U-Net**, and **Residual Attention U-Net**. These models are trained and evaluated on the **Massachusetts Roads Dataset** to segment road pixels in satellite imagery.

The project is structured as follows:

* **Data Preparation:** Loading, preprocessing, and visualization of images and masks from the dataset.
* **Model Implementation:** Custom PyTorch modules for the base U-Net, attention gates, and residual blocks.
* **Training Pipeline:** Data loaders, optimizers, loss functions (e.g., Binary Cross-Entropy with Dice), and training loops.
* **Evaluation:** Metrics including **Accuracy**, **IoU (Intersection over Union)**, and **Dice Score**, with visualization of predictions.

The implementation supports **GPU acceleration** and includes utilities for hyperparameter tuning, data augmentation, and model checkpointing.

---

## Features

* Custom U-Net architecture with encoder-decoder structure and skip connections.
* Attention U-Net with **attention gates** for focusing on relevant features and reducing noise.
* Residual Attention U-Net combining **residual blocks** for deeper networks and improved gradient flow.
* Dataset handling for the Massachusetts Roads Dataset (TIFF images and binary masks).
* Data augmentation using torchvision transforms (e.g., random flips, rotations).
* Training with **Adam optimizer**, **BCE-Dice loss**, and early stopping.
* Comprehensive evaluation metrics: Accuracy, IoU, Dice Score.
* Visualization tools for comparing ground truth masks with model predictions.
* GPU/CPU compatibility with configurable batch sizes and image resolutions (e.g., 256x256).

---

## Results

| Model                  | IoU Score | Dice Score | Validation Loss |
|------------------------|----------------|-----------------|---------------|
| U-Net                 | 0.68           | 0.81            | 0.61          |
| Attention U-Net       | 0.68           | 0.80            | 0.61          |
| Residual Attention U-Net | 0.69       | 0.81            | 0.60          |

# 🚀 Phase 2: Soft Actor-Critic (SAC) Project

## Overview

This phase implements **Soft Actor-Critic (SAC)**, a modern reinforcement learning algorithm that combines the strengths of **actor-critic methods** with **maximum entropy reinforcement learning**.  
Our project is structured in multiple parts:

* **Part 1:** Implemented dataset handling and preprocessing utilities.  
* **Part 2:** Implemented the core reinforcement learning pipeline, including:  
  * Replay Buffer for experience storage.  
  * Actor, Critic, and Value networks.  
  * The SAC Agent class with training (`learn`) and action selection (`choose_action`) routines.  

The implementation is built with **PyTorch**, supports **continuous action spaces**, and is suitable for environments such as **PyBullet** and **Gym**.  

---

## Features

* Replay Buffer with efficient batch sampling.  
* Actor-Critic architecture with **two Q-networks** to mitigate overestimation bias.  
* Value and Target Value networks for stable training.  
* Policy gradient updates with **reparameterization trick**.  
* Polyak averaging for target network updates.  
* GPU/CPU support.  

---

## Results

We trained our agent on **HalfCheetahBulletEnv-v0** and achieved:

```
Score:    2362.82 | Best score:    2362.82 | Avg score:    2141.81
```

within just **500 episodes** of training.

> 🎥 Sample output video :
> [Watch Training Video](rl-video-episode-499.mp4)

We also tested on **HalfCheetah-v4** from Gymnasium, where the agent appeared to move **faster and smoother**, but we did not record official runs yet.

---
