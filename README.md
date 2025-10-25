# Vision Model Comparison

### Implementation and evaluation of CNN and Transformer-based vision architectures across multiple datasets.

---

## Overview
This repository explores how computer vision architectures have evolved from classic **CNNs** to modern **Vision  (ViTs)**.  
Each model is implemented **from scratch in PyTorch** and trained on a unique dataset to analyze **accuracy**, **efficiency**, and **computational trade offs**.

---

## Implemented Architectures

| Model | Dataset | Description | Test Accuracy |
|--------|----------|--------------|-----------|
| **Vision Transformer (ViT)** | EuroSAT | Transformer-based model using image patches |     89% | 
| **EfficientNet** | Intel Images | Compound scaling for balanced accuracy & efficiency |     86% |
| **MobileNetV2** | PlantVillage | Lightweight CNN using depthwise separable convolutions |    99% |
| **ResNet** | CIFAR-100 | Residual connections for deeper training |     69% |
| **VGG** | CIFAR-10 | Deep sequential CNN with 3×3 convolutions |     92% | 

---

## Repository Structure

Each subfolder contains:
- The **model notebook** (`.ipynb`)  
- **Training & evaluation results** (plots, metrics, etc.)  
- A dedicated **README** describing the *setup* and *findings*
