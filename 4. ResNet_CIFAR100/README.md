# ResNet on CIFAR-100 Dataset

## Overview
This project implements a **custom ResNet-style CNN** from scratch in PyTorch for **CIFAR-100 image classification**.  
The model is designed to achieve **high accuracy** while maintaining **low computational cost** and a **compact parameter*** count.

## References
- **Paper:** [Deep Residual Learning for Image Recognition (ResNet)](https://arxiv.org/abs/1512.03385)  
- **Dataset:** [CIFAR-100](https://www.cs.toronto.edu/~kriz/cifar.html) (via `torchvision.datasets`)

## Dataset Details
- **Total Images:** 60,000 (32×32 RGB)  
- **Classes:** 100 categories  
- **Split:** 50,000 training / 10,000 testing samples  

## Model Architecture
- **Structure:**  
  - 1 **STEM layer**  
  - 16 **BasicBlocks** (each with 2 convolutional layers)  
  - 1 **Fully Connected** layer (100 output classes)  
- **Total Parameters:** ~1.35M  
- **MACs:** ~73M  

## **Results**
| Metric | Train | Test |
|:-------|:------:|:----:|
| **Accuracy** | 79.76% | 68.91% |
| **Latency** | — | 27 ms |
| **Throughput** | — | 9,622 img/sec |

- **Training Time:** ~41 minutes (with mixed precision)  
- **Visuals:** Accuracy/Loss curves and confusion matrix are available in the `results/` folder.  

## **Key Takeaways**
- Custom **ResNet** achieves **strong accuracy** on CIFAR-100 with only **~1.3M parameters**.  
- **Mixed Precision Training** accelerates training with minimal accuracy trade-off.
## **Analysis**
- The model shows slight **overfitting**. Accuracy on the training set remains higher even after using **data augmentation** and **dropout**.

- Achieving higher accuracy with such a **lightweight model** and **low computational cost** is inherently challenging.
