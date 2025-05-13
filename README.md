# 🛡️ Jailbreak: Norm-Constrained Pixel Patch Attacks on ResNet-34

This repository contains the code, experiments, and results for **Deep Learning Project 3** at NYU Spring 2025. We investigate the adversarial robustness of deep convolutional neural networks (ResNet-34, ResNet-50, and DenseNet-121) against pixel-space and patch-based attacks.

🔗 **Notebook Viewer:**  
[View the Project Notebook on nbviewer](https://nbviewer.org/github/yaswanthkumardamarla-dev/epsilon-jailbreak-resnet34-adversarial-attacks/blob/main/DL_Project_3_final.ipynb)

📄 **Project Report:** See `DL_Project.pdf` in the repository for the detailed report.

---

## 📌 Overview

We explore the following attack strategies:

- **Fast Gradient Sign Method (FGSM)**
- **Projected Gradient Descent (PGD)**
- **Patch-based PGD (Patch PGD)**

Attacks are conducted on pre-trained models using the **ImageNet-1K** dataset subset (500 images), with metrics focused on **Top-1 / Top-5 Accuracy**, **perturbation magnitude**, and **inference time**.

---

## 🧪 Experimental Setup

### ✅ Models Evaluated:
- `ResNet-34` (baseline)
- `DenseNet-121`
- `ResNet-50`

All models are loaded from `torchvision.models` with pretrained weights.

### 📊 Evaluation Metrics:
- Top-1 and Top-5 Accuracy
- Average Perturbation Magnitude (L∞ norm)
- Attack Generation & Inference Time

---

## ⚔️ Adversarial Attacks

| Attack        | Parameters                               | Perturbation | Time (s) |
|---------------|-------------------------------------------|--------------|----------|
| **FGSM**      | ε = 0.02                                  | Global       | ~1.04    |
| **PGD**       | ε = 0.02, α = 0.005, 10 steps             | Global       | ~4.10    |
| **Patch PGD** | ε = 0.2, α = 0.019, 32×32 patch, 50 steps | Localized    | ~19.49   |

---

## 📈 Results Summary

| Model          | Clean Top-1 | FGSM | PGD  | Patch PGD |
|----------------|-------------|------|------|-----------|
| **ResNet-34**  | 76.0%       | 3.8% | 0.0% | 0.0%      |
| **DenseNet-121** | 74.6%     | 45.6%| 39.0%| 49.4%     |
| **ResNet-50**  | 80.2%       | 46.4%| 38.0%| 48.6%     |

---

## 🔍 Key Insights

- **ResNet-34** is highly vulnerable to all attack types.
- **DenseNet-121** and **ResNet-50** show better resilience, especially against patch attacks.
- Patch-based attacks retain high stealth and cause significant accuracy drops.

---

## 🛠️ How to Run

1. Clone the repo:
   ```bash
   git clone https://github.com/yaswanthkumardamarla-dev/epsilon-jailbreak-resnet34-adversarial-attacks.git
   cd epsilon-jailbreak-resnet34-adversarial-attacks
Run the notebook:
Open DL_Project_3_final.ipynb using Jupyter Notebook or Google Colab.

## 📁 Files in Repository
## 📁 Files in Repository

| File                     | Description                              |
|--------------------------|------------------------------------------|
| [`DL_Project_3_final.ipynb`](DL_Project_3_final.ipynb) | Full code implementation and evaluation |
| [`DL_Project.pdf`](DL_Project.pdf)                   | Complete project report and results     |
| [`README.md`](README.md)                             | Project overview and instructions       |


## 📚 References
Goodfellow et al., “Explaining and Harnessing Adversarial Examples”, ICLR 2015

Madry et al., “Towards Deep Learning Models Resistant to Adversarial Attacks”, ICLR 2018

Brown et al., “Adversarial Patch”, arXiv:1712.09665

Liu et al., “Delving into Transferable Adversarial Examples”, ICLR 2017

 ## 👨‍💻 Authors
Bhagya Rekha Deenadayal – bd2585

Yaswanth Kumar Damarla – yd3034

Bhanu Dileep Reddy Maryada – bm3539

📍 New York University, Tandon School of Engineering – Spring 2025
