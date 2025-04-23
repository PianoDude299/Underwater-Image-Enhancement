# Underwater Image Enhancement Using ResUNet with Perceptual Loss

## 📌 Project Overview
This project focuses on enhancing degraded underwater images using a deep learning approach.  
We implement a **ResUNet** architecture, combined with a **composite loss function** comprising **MSE**, **SSIM**, and **Perceptual Loss (VGG16-based)**, to improve both the numerical quality (PSNR) and the perceptual realism (SSIM) of underwater images.

The work is part of the course **BCSE403L - Digital Image Processing**, 6th Semester, VIT Chennai.

---

## 📚 Technologies and Libraries Used
- Python 3
- PyTorch
- torchvision
- pytorch-msssim
- scikit-image
- matplotlib
- PIL (Python Imaging Library)

---

## 📂 Dataset
- **UIEB (Underwater Image Enhancement Benchmark) Dataset**
- Dataset includes paired raw and ground truth clean underwater images.
- Images were resized to **256×256** for efficient training.

⚠️ **Note**: Due to GitHub file size restrictions, the dataset is not included in this repository.  
Please download the dataset separately from [UIEB Dataset Website](https://li-chongyi.github.io/proj_underwater.html) or request it if needed.

---

## 🏛 Model Architecture

- **Encoder-Decoder** structure (from U-Net) with **skip connections** for better feature preservation.
- **Residual Blocks** (from ResNet) for stable and deep feature learning.
- Final activation with **Sigmoid** to map outputs to the range [0, 1].

---

## 🎯 Loss Function

The total loss used for training is:

\[
\text{Total Loss} = 0.7 \times \text{MSE Loss} + 0.2 \times (1 - \text{SSIM}) + 0.1 \times \text{Perceptual Loss (VGG16)}
\]

- **MSE Loss**: Minimizes pixel-wise error (improves PSNR)
- **SSIM Loss**: Maintains structural similarity (improves edge/contrast)
- **Perceptual Loss**: Enhances textural and visual realism using intermediate VGG16 features

---

## 📈 Results

| Metric | Value |
|--------|-------|
| **PSNR** | 24.17 |
| **SSIM** | 0.9450 |

- Achieved a significant improvement compared to basic autoencoders.
- Outputs are visually sharper, better colored, and more natural-looking.

---

## 🚀 How to Run

1. Install the required libraries:
   ```bash
   pip install torch torchvision pytorch-msssim matplotlib scikit-image pillow

2. Clone the repo and move into it:
