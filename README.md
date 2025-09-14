---

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
