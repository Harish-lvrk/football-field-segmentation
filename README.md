#  Football Field Segmentation Using Deep Learning

##  Project Summary

This project implements semantic segmentation on football match images using deep learning. The main objective is to identify and segment key elements on the field—such as players, the ball, and the pitch itself. The project is built with **PyTorch**, and leverages a labeled image dataset from **Kaggle**.

---

## Dataset Details

- **Source**: [Football Semantic Segmentation Dataset on Kaggle](https://www.kaggle.com/datasets/sadhliroomyprime/football-semantic-segmentation)

- **Contents**:
  - 100 original images
  - 100 corresponding mask images
  - 100 saved output images

- **Data Split**:
  - Training set: 80 image pairs  
  - Validation set: 10 image pairs  
  - Testing set: 10 image pairs
  - number of classes:  11

---

## Models Implemented

The following segmentation architectures were explored:

- U-Net (Baseline)
- Modified U-Net
- Attention-based U-Net
- U-Net with ResNet-50 backbone
- U-Net with ResNet-101 backbone

---

##  Training Configuration

- **Initial Learning Rate**: 0.001
- **Loss Function**: Combined Dice Loss + Focal Loss (hybrid loss)
- **Epochs, batch size**, and other hyperparameters remain consistent across models for fair evaluation.

---

##  Evaluation Metrics

To evaluate segmentation performance, we used:

- **Dice Coefficient**: to assess overlap quality  
- **Loss Curves**: to track training and validation convergence

---

##  Test Results (LR = 0.001 )

| Model Variant         | Test Loss | Dice Score |
|-----------------------|-----------|------------|
| U-Net (Baseline)      | 0.2204    | 0.7432     |
| Modified U-Net        | 0.2268    | 0.6297     |
| Attention U-Net       | 0.2512    | 0.5806     |
|  ResNet-50            | 0.2274    | 0.6495     |
| ResNet-101            | 0.2300    | 0.5955     |

---

##  Conclusion

This project demonstrates that for football image segmentation, a well-tuned Baseline U-Net model can outperform more complex architectures such as Attention U-Net and ResNet-based U-Nets, especially on limited datasets. The hybrid Dice + Focal loss function effectively handled class imbalance, resulting in satisfactory segmentation accuracy.

The results highlight that model simplicity, combined with appropriate loss functions and training strategies, can yield strong performance even with small datasets. Future work could explore more advanced augmentation, backbone variations, and post-processing for further improvements.
