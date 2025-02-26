# Swin-Tiny Transformer Fine-Tuning

## Overview

This repository contains a Jupyter Notebook for fine-tuning the **Swin-Tiny Transformer** on a **custom multi-class image dataset**. The model is trained using **transfer learning**, leveraging pre-trained ImageNet weights for feature extraction and fine-tuning.

## Dataset

- The model is trained on a **custom image dataset** with **4 classes**.
- Ensure your dataset is organized as follows:
  ```
  dataset/
  ├── train/
  │   ├── class_1/
  │   ├── class_2/
  │   ├── class_3/
  │   ├── class_4/
  ├── val/
  │   ├── class_1/
  │   ├── class_2/
  │   ├── class_3/
  │   ├── class_4/
  ```

## Model Architecture

- **Model:** Swin-Tiny (`swin_t` from `torchvision.models`)
- **Pretrained Weights:** ImageNet
- **Output:** Fully connected layer with 4 output classes

## Training Details

- **Optimizer:** AdamW / SGD (momentum-based)
- **Loss Function:** CrossEntropyLoss
- **Epochs:** 100
- **Learning Rate Scheduler:** StepLR / Cosine Annealing
- **Data Augmentation:** Random Resized Crop, Horizontal Flip, Normalization

## Evaluation

- **Metrics:** Accuracy, Loss
- **Performance Tracking:** Uses `tqdm` for real-time progress tracking

## Test Results

- The model was tested on a separate validation set.
- **Final Test Accuracy:** 99.00%
- **Loss:** 4.34%
- **Confusion Matrix:** Shows strong classification performance across all classes.
