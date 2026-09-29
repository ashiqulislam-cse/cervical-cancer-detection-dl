Project Title : Explainable AI for Cervical Cancer Detection using Histopathological Images

Dataset used for the project

CAISHI / CAISHI Dataset (Size ~ 10 GB)

About dataset

CAISHI is a dataset containing 2240 cervical histopathological images, of which 1010 are of normal cervical glands and 1230 are of cervical adenocarcinoma in situ (AIS), i.e. abnormal. The images were obtained using an endoscopic biopsy sampling method, followed by pathological section preparation with H&E staining at Shengjing Hospital of China Medical University. The images were captured at 100× magnification using an Axio Scope.A1 microscope, with a resolution of 3840 × 2160 pixels and .png format.

Link to the dataset:
https://figshare.com/articles/figure/MIaMIA-Open-Data-Cervical-AIS-Histopathology-Image_CASIHI/24548953

Transfer Learning - MobileNetV3 Salient Features

Hardware-Aware NAS → Lower latency

Hard-Swish Activation → Efficient non-linear feature learning

SE (Squeeze-and-Excitation) Blocks → Stronger feature representation

Inverted Residuals + Depthwise Separable Convolutions → Computational efficiency

MobileNetV3-Large → Balance between model capacity and computational cost

Model Used

MobileNetV3-Large with ImageNet-pretrained weights was used for transfer learning.

Framework: PyTorch / Torchvision

Input size: 224 × 224

Classes: Abnormal (AIS) and Normal

Loss function: Cross-Entropy Loss

Optimizer: Adam

Learning rate: 0.001

Weight decay: 0.0001

Batch size: 32

Training epochs: 25

Classifier: Linear → ReLU → Dropout → Linear

Data augmentation: Random crop, horizontal flip, rotation and color jitter

Evaluation: Accuracy, Precision, Recall, F1-score and Confusion Matrix

Dataset Split

The implementation divides the available images into:

64% Training

16% Validation

20% Testing

The supplied training run processed 2,242 image files after extraction and splitting. The project description lists the CAISHI dataset as 2,240 images; the difference should be treated as a dataset/file-count discrepancy rather than assumed to be a different dataset version.

Results

Validation Performance

Best Validation Accuracy: 91.62%

Best validation performance was recorded at Epoch 15.

Held-Out Test Performance

Test Samples: 448

Correct Predictions: 404

Test Accuracy: 90.18%

Classification Report

Class

Precision

Recall

F1-Score

Abnormal

0.92

0.90

0.91

Normal

0.88

0.91

0.89

Overall Accuracy





0.90

Explainable AI - Grad-CAM

The project also implements Grad-CAM (Gradient-weighted Class Activation Mapping) to visualize the regions of histopathological images that contribute to the model prediction.

This provides an interpretable heatmap over the input image and helps examine which visual regions the trained MobileNetV3 model uses for classification.

Project Workflow

Dataset → Preprocessing → Data Augmentation → Train/Validation/Test Split → MobileNetV3-Large Transfer Learning → Model Training → Evaluation → Confusion Matrix → Grad-CAM Explainability

Technologies Used

Python

PyTorch

Torchvision

NumPy

Pillow

OpenCV

Scikit-learn

Matplotlib

Seaborn

Grad-CAM

Google Colab
