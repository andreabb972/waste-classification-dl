# Waste Image Classification using Deep Learning

[![Python](https://img.shields.io/badge/Python-3.11+-blue.svg)](https://www.python.org/)
[![PyTorch](https://img.shields.io/badge/PyTorch-2.0+-red.svg)](https://pytorch.org/)
[![Grade](https://img.shields.io/badge/Grade-19%2F20-success.svg)]()

This repository presents an image classification pipeline applied to the **RealWaste** dataset (9 classes, 4,279 training images). This project was developed in a team of two, as part of the **Deep Learning course at Polytech Nice Sophia (2025)**, taught by **Gaëtan Bahl** (Principal Machine Vision Engineer at NXP), and was **awarded a grade of 19/20**.

**[Read the Full Project Report (PDF)](https://github.com/andreabb972/waste-classification-dl/blob/main/report.pdf)**

---

## Key Features & Methodology

1. **Progressive Fine-Tuning Strategy**: 
   - **Phase 1**: Freezing the pre-trained backbone and training only the classification head.
   - **Phase 2**: Partial unfreezing of deeper layers.
   - **Phase 3**: Full unfreezing with low learning rates and AdamW optimizer.
2. **Backbone Exploration & Ensembling**:
   - Evaluated multiple state-of-the-art architectures: *DenseNet*, *ConvNeXt-Tiny*, *EfficientNetV2-M*, and *Swin-T (Vision Transformer)*.
   - Implemented a **Weighted Ensemble** combining ConvNeXt, Swin-T, and EfficientNetV2-M, achieving **97% test accuracy**.
3. **Edge AI & Export**:
   - Explored cost-accuracy trade-offs (comparing lightweight models like MobileNet).
   - Converted `.pth` models to **ONNX** and **TFLITE** formats and benchmarked execution speed.

---

## Summary of Results

| Model / Strategy | Architecture Type | Test Accuracy | Model Size |
| :--- | :--- | :--- | :--- |
| DenseNet (Fine-tuned) | CNN | 86% | - |
| ConvNeXt-Tiny | CNN (Transformer-inspired) | 95% | 109 MB |
| **Three-Model Ensemble** | Ensemble (ConvNeXt + Swin + EfficientNet) | **97%** | 424 MB |
| MobileNet-Large | Lightweight CNN | 94% | 16 MB |

---

## Repository Structure

- `projet_git.ipynb` : The main Jupyter Notebook containing the structured end-to-end pipeline (data augmentation, model initialization, training, evaluation, and ensembling).
- `report.pdf` : The complete technical report detailing theoretical choices and experiment analyses (graded 19/20).
- `requirements.txt` : Python dependencies.

---

## Getting Started

1. Clone the repository:
   ```bash
   git clone [[[https://github.com/votre-nom-utilisateur/waste-classification-dl.git](https://github.com/votre-nom-utilisateur/waste-classification-dl.git)](https://github.com/andreabb972/waste-classification-dl.git)](https://github.com/andreabb972/waste-classification-dl.git)
   cd waste-classification-dl
   pip install -r requirements.txt
