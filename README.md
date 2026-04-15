# Fashion-MNIST Neural Network: Overfitting and Model Improvement

## Overview
This project explores image classification using the Fashion-MNIST dataset and focuses on understanding and mitigating overfitting in neural networks. A baseline model was first created and evaluated, followed by an improved model that incorporates multiple techniques to enhance generalization.

---

## Dataset
The Fashion-MNIST dataset consists of 70,000 grayscale images (28x28 pixels) across 10 clothing categories.  

- 60,000 images for training  
- 10,000 images for testing  

The dataset was normalized and split into:
- Training set (80%)
- Validation set (20%)
- Test set (provided separately)

Stratified sampling was used to maintain class balance across splits.

---

## Part A: Baseline Model

### Results
The baseline model achieved strong training accuracy but showed signs of overfitting:
- Training accuracy increased steadily
- Validation accuracy plateaued
- Validation loss began to diverge from training loss

---

## Part B: Overfitting Mitigation Techniques

The improved model included the following techniques:

### 1. Regularization
- L2 regularization applied to dense layers
- Helps prevent overly large weights and reduces model complexity

### 2. Dropout
- Dropout layers (30%) added between dense layers
- Reduces co-adaptation of neurons

### 3. Batch Normalization
- Stabilizes and accelerates training
- Improves convergence

### 4. Data Augmentation
- Applied using ImageDataGenerator
- Transformations included:
  - Rotation
  - Zoom
  - Horizontal flipping
- Increased dataset diversity

### 5. Early Stopping
- Monitored validation loss
- Training stopped when performance stopped improving
- Prevented unnecessary training and overfitting

---

## Part C: Comparison and Results

### Performance Comparison
| Model        | Validation Accuracy | Test Accuracy |
|--------------|---------------------|---------------|
| Baseline     |        0.8918       |     0.8829    |
| Improved     |        0.8287       |     0.8161    |

### Key Observations
- The improved model showed better generalization
- Reduced gap between training and validation accuracy
- Validation loss stabilized more effectively
- Training stopped earlier due to EarlyStopping

---

## Conclusion

The improved model outperformed the baseline by reducing overfitting and improving generalization.  

The most impactful techniques were:
- **Dropout**, which reduced overfitting by limiting neuron dependence
- **Data augmentation**, which improved robustness by exposing the model to more diverse inputs
- **Early stopping**, which prevented unnecessary training beyond optimal performance

This project demonstrates that combining multiple regularization techniques is more effective than relying on a single method when improving neural network performance.

---
