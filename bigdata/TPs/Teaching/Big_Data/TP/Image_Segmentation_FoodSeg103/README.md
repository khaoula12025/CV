# Big Data TP — FoodSeg103 Image Segmentation

This practical work focuses on image segmentation using the **FoodSeg103** dataset and a U-Net architecture with a **ResNet101 encoder**.

## 1. Baseline Model

The baseline implements a U-Net with a ResNet101 encoder trained on the original FoodSeg103 dataset.

The baseline experiment is used as a reference for evaluating the impact of data augmentation and synthetic data generation.

* Training: 10 epochs
* Architecture: U-Net + ResNet101
* Dataset: FoodSeg103
* Evaluation metrics: Loss, mIoU, Dice, and Accuracy
* Baseline model weights: `unet_resnet101_baseline_final.pth`
* Training history: `unet_resnet101_baseline_history.csv`

## 2. Synthetic Data Generation with Stable Diffusion

A second part of the practical work explores the generation of synthetic food images using **Stable Diffusion**.

The generated images are used to increase the diversity of the training data. Pseudo-labels are initially generated automatically and subsequently verified using segmentation and vision-language models.

> The **1AD activity corresponds to the Stable Diffusion-based synthetic data generation component. It is not the baseline experiment.**

## 3. Verified Synthetic Dataset

The augmented dataset includes synthetic images together with verified masks and labels.

The verification pipeline uses **SAM (Segment Anything Model)** and **CLIP** to improve the reliability of the generated annotations.

## 4. Improved Segmentation Model

Students are asked to improve the augmented segmentation model by:

* increasing the number of training epochs;
* experimenting with **Dice + BCE Loss**;
* optionally testing **Focal Loss**, combined with Dice Loss or used independently;
* reporting appropriate segmentation metrics;
* comparing the improved model with the baseline.

### Evaluation Metrics

The experiments should report:

* **mIoU (mean Intersection over Union)**
* **Dice coefficient**
* **Accuracy**
* **Loss**
* **F1-score**

The metrics should be reported for both the **training** and **validation** sets.

## Learning Objectives

Through this practical work, students explore:

* semantic image segmentation;
* U-Net architectures;
* ResNet-based encoders;
* transfer learning and fine-tuning;
* data augmentation;
* synthetic data generation with Stable Diffusion;
* automatic and verified pseudo-label generation;
* segmentation loss functions;
* model evaluation and comparison.
