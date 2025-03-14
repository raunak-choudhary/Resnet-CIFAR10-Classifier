# CIFAR-10 Image Classification with Modified ResNet

## Team Information

**Team Name:** Decoders  

### Team Members:
- **Raunak Choudhary** ([raunak.choudhary@nyu.edu](mailto:raunak.choudhary@nyu.edu), NetID: rc5553)  
- **Debika Dharma Lingam** ([dd3873@nyu.edu](mailto:dd3873@nyu.edu), NetID: dd3873)  
- **Yashavika Singh** ([ys6668@nyu.edu](mailto:ys6668@nyu.edu), NetID: ys6668)  

---

## 📌 Project Overview
This project implements a **modified ResNet architecture** for CIFAR-10 image classification, optimized to achieve high accuracy while keeping the **parameter count under 5 million**.  

- ✅ **Achieved Validation Accuracy:** **95.60%**  
- ✅ **Total Parameters:** **4,969,600** (Under the 5M limit)  

---

## 🏗 Model Architecture
We have designed an **improved Pre-Activation ResNet** with several enhancements:

- **Pre-activation Residual Blocks**  
  - Batch normalization & activation **before** convolutions → **Better gradient flow**  
- **Mish Activation Function** (`x * tanh(softplus(x))`)  
  - Replaces ReLU for **smoother gradient propagation**  
- **Attention Mechanisms**  
  - **CBAM (Convolutional Block Attention Module)** for **channel & spatial attention**  
- **Strategic Channel Progression:**  
  - Optimized dimensions: **30 → 60 → 120 → 240**  
  - **Balances parameter count & feature representation**  
- **Optimized Residual Block Structure:**  
  - **[2, 2, 5, 3]** → **Deep representations without excessive parameters**  

---

## 🔥 Training Approach
Our training methodology includes **advanced techniques** for better generalization & robustness:

- **📌 One-Cycle Learning Rate Schedule** → Faster convergence  
- **📌 Label Smoothing** → Prevents overconfidence  
- **📌 CutMix Data Augmentation** → Combines multiple images for robustness  
- **📌 Comprehensive Augmentations** → Crops, flips, color jittering, random erasing  
- **📌 AdamW Optimizer** → Improved weight decay regularization  

---

## 📊 Results

| Metric                 | Value                 |
|------------------------|----------------------|
| **Model Size**         | 4,969,600 parameters |
| **Best Validation Accuracy** | **95.60%** |
| **Training Time**      | ~75 minutes         |

---

## 🛠 Installation & Requirements
To run the project, install the following dependencies:

```bash
pip install numpy pandas torch torchvision matplotlib Pillow scikit-learn
