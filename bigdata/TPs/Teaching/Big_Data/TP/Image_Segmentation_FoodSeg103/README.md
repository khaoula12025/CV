# Big Data TP — FoodSeg103 Image Segmentation

This practical work focuses on image segmentation using the **FoodSeg103** dataset and a U-Net architecture with a **ResNet101 encoder**.
### 📦 Baseline & Augmented Files

All baseline and augmented resources are available in the following Google Drive folder:

**[Download / Access all project files](https://drive.google.com/drive/u/0/folders/1g1itMD3iaXQ4Ra2wvbgaYMx8l9Hy2Ix4)**


## 1. Baseline Model

The baseline implements a U-Net with a ResNet101 encoder trained on the original FoodSeg103 dataset for 10 epochs.

* **Architecture:** U-Net + ResNet101
* **Dataset:** FoodSeg103
* **Training:** 10 epochs
* **Purpose:** Reference model for comparison with the augmented approach

### Baseline Files

* **Baseline Notebook:** [Open the baseline notebook](https://drive.google.com/file/d/18pU_x-XjCBRU2yDdwPl8XKefv6d6SJT0/view?usp=drive_web)
* **Baseline Model Weights (.pth):** [Download the baseline model](https://drive.google.com/file/d/17XLU0E_HBEViGmLeiSJ_21EsJcoD5A-n/view?usp=drive_web)
* **Baseline Training History (.csv):** [Open the training history](https://drive.google.com/file/d/1s2kw81ySxZpcy3DpsFRxv6hW_cENKViY/view?usp=drive_web)

The baseline provides the reference results against which the improved model is evaluated.

## 2. Synthetic Data Generation with Stable Diffusion

A synthetic dataset was created using **Stable Diffusion** to generate additional food images from text prompts.

The generated images are then processed to obtain pseudo-labels. These synthetic data are used to increase the diversity of the training set.

> **Important:** The **1AD file corresponds to the Stable Diffusion / synthetic data generation activity. It is not the baseline.**

### Synthetic Dataset

* **`synthetic-data-foodseg`** — Synthetic images generated using Stable Diffusion, together with automatically generated pseudo-labels.
* **`pseudo_labels.jsonl`** — Raw pseudo-label annotations.

## 3. Verified Synthetic Dataset

The synthetic annotations are further processed and verified using **SAM (Segment Anything Model)** and **CLIP**.

* **`verified-masks-labels-foodseg`** — Dataset containing verified segmentation masks and labels.
* **`verified_masks/*.npy`** — Verified segmentation masks.
* **`verified_labels.jsonl`** — Verified labels.

These verified synthetic data are used by the augmented segmentation notebook.

## 4. Augmented Segmentation Model

The notebook whose filename ends with **`85.ipynb`** corresponds to the augmented version using:

* FoodSeg103;
* synthetic images generated with Stable Diffusion;
* verified masks and labels;
* SAM + CLIP-based verification.

### Students are asked to improve the model by:

* increasing the number of training epochs;
* experimenting with **Dice + BCE Loss**;
* optionally testing **Focal Loss**;
* reporting **mIoU, Dice, Accuracy, Loss, and F1-score**;
* reporting results for both training and validation;
* comparing the improved model with the baseline.

## 5. Learning Objectives

Students will work with:

* semantic image segmentation;
* U-Net architectures;
* ResNet-based encoders;
* transfer learning and fine-tuning;
* data augmentation;
* synthetic data generation using Stable Diffusion;
* pseudo-label generation;
* SAM and CLIP-based verification;
* segmentation loss functions;
* model evaluation and comparison.
