
# Vision Transformer (ViT) on EuroSAT Dataset

## Overview
This project implements a **custom Vision Transformer (ViT)** from scratch in **PyTorch** for the **EuroSAT Land Classification dataset**.  
The model is designed to achieve a strong balance between **accuracy, model size, and computational efficiency**. 

## References
- **Paper:** [An Image is Worth 16x16 Words: Transformers for Image Recognition at Scale](https://arxiv.org/abs/2010.11929)  
- **Dataset:** [EuroSAT Dataset (RGB)](https://www.kaggle.com/datasets/apollo2506/eurosat-dataset)

## Dataset
- **Total Images:** 27,000 RGB satellite images size of (64×64×3)  
- **Classes:** 10 land use categories (*AnnualCrop, Forest, HerbaceousVegetation, Highway, Industrial, Pasture, PermanentCrop, Residential, River, SeaLake*)  
- **Split:** Standard 80% training / 20% testing split  

## Model Architecture
- **Structure:** Custom **Vision Transformer (ViT)** implemented from scratch with patch embeddings, multi-head self-attention, and feed forward encoder blocks.  
- **Patch Size:** 8×8 
- **Parameters:** **3.1M**  
- **MACs:** **215.38M**  
- **Input Size:** 64×64  
- **Precision:** Full precision (FP32) for stable convergence  

---

## Results
| Metric | Train | Test |
|:--------|:-------:|:------:|
| **Top-1 Accuracy** | 87.80% | 89.28% |
| **Top-2 Accuracy** | 96.63% | 97.26% |

- **Epochs:** 50  
- **Training Precision:** FP32 (Full Precision)  
- **Time per Batch:** **12 ms** (128 batch size)
- **Throughput:** **10,590 images/sec**  
- **Visuals:** Accuracy and loss curves are available in the `results/` folder  

---

## Mixed Precision Training Note
During experimentation, training the ViT from scratch on EuroSAT with **mixed precision (FP16)** caused the model’s accuracy to **decrease continuously**.  
I think this behavior is caused by:
- **Numerical instability** in attention and normalization layers,  
- **Gradient underflow** in FP16 arithmetic, and  
- **Small dataset size**.  

To ensure stable convergence, **full precision (FP32)** training was used.  
Mixed precision may work well when a **pre-trained ViT backbone** was used.

---

## Key Insights
- The custom ViT achieved **high accuracy** and **strong generalization** despite being trained from scratch.  
- **Lightweight design (3.1M params)** and **low MAC count** make it ideal for efficient inference.  
- The model’s **Top-2 accuracy (97.26%)** shows it captures strong interclass relationships.  
- Full precision training ensured **stable optimization** and prevented performance collapse.
