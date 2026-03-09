# Cancer Detection in Histopathology Images using ResNet-34

This project investigates the impact of different learning rate scheduling strategies when training a ResNet-34 convolutional neural network on the PatchCamelyon (PCam) histopathology dataset.

The goal is to analyze how learning rate schedules affect training dynamics, convergence behaviour, and generalization performance in deep neural networks.

---

## Dataset

The PatchCamelyon (PCam) dataset is a benchmark dataset for cancer detection in histopathology images.

- Binary classification task: tumor vs non-tumor tissue
- Extracted patches from whole-slide histopathology images
- Training, validation, and test splits provided by the dataset

Dataset link:
https://github.com/basveeling/pcam

---

## Model

A **ResNet-34 convolutional neural network** was used for classification.

Architecture highlights:

- Deep residual network with skip connections
- Final fully connected layer adapted for binary classification
- Random weight initialization (no pretrained weights)

---

## Training Setup

Training configuration:

- Optimizer: Stochastic Gradient Descent (SGD)
- Momentum: 0.9
- Weight decay: 5 × 10⁻⁴
- Batch size: 64
- Training epochs: 60

Data augmentation:

- Random horizontal flips
- Random rotations (±10°)

---

## Learning Rate Scheduling Strategies

Five learning rate schedules were evaluated:

1. **Constant learning rate**
2. **Step decay**
3. **Cosine annealing**
4. **Cosine annealing with warm restarts**
5. **Linear warmup followed by cosine decay**

All schedules were tested under the same training configuration to ensure a fair comparison.

---

## Evaluation Metrics

Model performance was evaluated using:

- Accuracy
- F1-score
- ROC-AUC

Each experiment was repeated with **three random seeds (42, 43, 44)** and results were averaged to account for stochastic variability.

---

## Key Findings

The experiments show that learning rate scheduling significantly influences optimization behaviour and final performance.

- Simple schedules such as **constant learning rate** provide fast early convergence.
- Smooth schedules like **cosine annealing** produce more stable training dynamics.
- **Warmup + cosine decay** helps stabilize early training while maintaining strong generalization.

Overall, carefully designed learning rate schedules improve both convergence stability and model generalization.

---

## Repository Structure
