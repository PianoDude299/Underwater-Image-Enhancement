# Underwater Image Enhancement Using ResUNet with Perceptual Loss

## 📌 Project Overview
This project focuses on enhancing degraded underwater images using a deep learning approach.  
We implement a **ResUNet architecture**, combined with a composite loss function of **MSE**, **SSIM**, and **Perceptual Loss (VGG16-based)**, to improve both numerical quality (PSNR) and perceptual realism (SSIM) of underwater images.

The project was developed for the course **BCSE403L - Digital Image Processing**, Semester 6, Slot A2+TA2, VIT Chennai.

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
- **Dataset Used**: UIEB (Underwater Image Enhancement Benchmark)
- Contains paired raw and reference clean underwater images.
- Images resized to **256x256** during preprocessing.

⚠️ **Note**: Due to GitHub file size restrictions, the dataset is not uploaded here.  
Please download it separately from [UIEB Dataset Website](https://li-chongyi.github.io/proj_underwater.html).

---

## 🏛 Model Architecture

- **ResUNet**: Encoder-Decoder structure with skip connections (U-Net) + Residual Blocks (ResNet).
- Final activation: **Sigmoid** function for mapping outputs between [0, 1].

---

## 🎯 Loss Function

Total loss used during training:

\[
\text{Total Loss} = 0.7 \times \text{MSE} + 0.2 \times (1 - \text{SSIM}) + 0.1 \times \text{Perceptual Loss (VGG16)}
\]

**Loss Components:**
- **MSE Loss**: Minimizes pixel-wise errors.
- **SSIM Loss**: Preserves structural similarity.
- **Perceptual Loss**: Enhances textural realism using pretrained VGG16 feature maps.

---

## 📈 Results

| Metric | Value |
|--------|-------|
| PSNR   | 24.17 |
| SSIM   | 0.9450 |

✅ Significant improvement in underwater image clarity and realism compared to baseline autoencoder models.

---

## 🚀 How to Run the Project

1. Install the required libraries:
    ```bash
    pip install torch torchvision pytorch-msssim matplotlib scikit-image pillow
    ```

2. Clone this repository:
    ```bash
    git clone https://github.com/<your-username>/underwater-image-enhancement.git
    cd underwater-image-enhancement
    ```

3. Open the Jupyter Notebook:
    - Navigate to `/Code/Underwater_Image_Enhancement.ipynb`
    - Run the cells sequentially for training and evaluation.

---

## 🗂 Repository Structure

```plaintext
/Code/
    └── Underwater_Image_Enhancement.ipynb
/Documents/
    ├── BasePaper.pdf
    └── ReferencePapers/
        ├── ref1.pdf
        ├── ref2.pdf
        └── ...
/Presentation/
    └── ProjectSlides.pptx (Coming soon)
/DraftPaper/
    ├── PaperDraft.docx (Coming soon)
    └── PaperDraft.pdf (Coming soon)
README.md
