
# VGG on CIFAR10 Dataset

## Overview
This project implements a **custom VGG-style CNN** from scratch in PyTorch for **CIFAR-10 image classification**.  
The model is designed to achieve **high accuracy** while maintaining **low computational cost** and a **compact parameter*** count.

## References
- **Paper:** [VERY DEEP CONVOLUTIONAL
NETWORKS(VGG)](https://arxiv.org/pdf/1409.1556)  
- **Dataset:** [CIFAR-10](https://www.cs.toronto.edu/~kriz/cifar.html) (via `torchvision.datasets`)

## Dataset Details
- **Total Images:** 60,000 (32×32 RGB)  
- **Classes:** 10 categories  
- **Split:** 50k training / 10k testing samples  

## Model Architecture
- **Structure:**  
  - 8  `conv-bn-relu` blocks
  - 4 `maxpool` layers
  - 2 **Fully Connected** layer (10 output classes)  
- **Total Parameters:** ~4.7M  
- **MACs:** ~210M  

## **Results**
| Metric | Train | Test |
|:-------|:------:|:----:|
| **Accuracy** | 95.84% | 92.38% |

- **Training Time:**  ~12.5 minutes (with mixed precision)  
- **Visuals:**  Accuracy/Loss curves and confusion matrix are available in the `results/` folder.  

## **Key Takeaways**
- Customized **VGG** achieves **strong accuracy** on CIFAR-10 with only **~4.7M parameters**.  
- **Mixed Precision Training** accelerates training with minimal accuracy trade-off.
