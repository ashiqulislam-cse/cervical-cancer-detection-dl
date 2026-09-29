# Repository Verification Notes

This document records important distinctions between the academic report and the supplied source notebook.

## Directly supported by the supplied code

- The implementation uses PyTorch/torchvision MobileNetV3-Large.
- The dataset is split 64% train, 16% validation, 20% test.
- The recorded split contains 2,242 images.
- The best recorded validation accuracy is 91.62%.
- The recorded held-out test accuracy is 90.18% (404/448).
- The classification report is 0.92/0.90/0.91 for abnormal and 0.88/0.91/0.89 for normal.
- Grad-CAM is implemented for a MobileNetV3 feature layer.

## Not present in the supplied code file

A ResNet50 implementation is not present in the supplied code attachment. If a ResNet50 notebook/script exists, add it separately rather than creating a new implementation and presenting it as the original experiment.

## Report/code discrepancy

The academic report contains different dataset/result descriptions, including a reported MobileNetV3 accuracy of approximately 96.73%. The supplied executable code instead records 90.18% on a 448-image held-out test set. The GitHub README therefore uses the directly observed code result and does not silently replace it with the report's figure.

Before publishing a final model-comparison claim, reconcile the report, original ResNet50 code, and original experiment outputs.
