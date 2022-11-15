# Facial-Detection
Implement ResNet-50 for Facial Detection Kaggle competition

Facial Recognition Task Accuracy 89.4%
Verification Task Accuracy 62.8%

To run, train on the ResNet50 architecture code cell. Once trained, save model. Either run evaluation/prediction one model or
use the ensemble prediction functions by loading each model and data loader in a list.

<img width="1030" alt="image" src="https://user-images.githubusercontent.com/57874328/202045013-21cf7038-ffcd-4507-af59-5d35b32883ce.png">

https://wandb.ai/akh/hw2p2?workspace=user-akh

Data augmentation experiments:
Normalization
RandomHorizontalFlip
ColorJitter
GaussianBlur
RandomRotation
RandomAutocontrast
RandomAdjustSharpness (Not used)

Other experiments:
ResNet34 vs ResNet50 vs ResNet101 vs ResNet 150 (Used 50)
Extra classification layers (Not used)
ReduceLRonPlateau vs CosineAnnealing (Used Cos)
Weight Decay 1e-4 to 1e-3

Final model was ensemble of two ResNet50 models with these differences:
1. Weight Decay 5e-4, MinMax data normalization, All data augmentation but Rotation and Autocontrast, 100 epochs
2. Weight Decay 2.5e-4, No data normalization, All data augmentation, 120 epochs
