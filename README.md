# DeepBrain

A project guided by Dr J Manikandan(Placement and Training department) team members -Vedant Patil,Saksham Kumar Singh,Harshit Arora,Ishan Pardi,Anuj rai

Automated brain tumor detection from MRI with deep learning. Uses transfer learning with ResNet-50 to classify glioma, meningioma, pituitary tumors, or healthy brains. Achieves 94% test accuracy. Empowers faster, reliable medical diagnostics.
Model Architecture Overview
Base Model: ResNet50 (pre-trained on ImageNet, include_top=False, input size: 150×150×3)

Weights: Pre-trained ImageNet

Trainable Parameters: All original ResNet50 convolutional layers are frozen (not trainable during your training phase).

Custom Top Layers (added for classification on your brain tumor dataset):

GlobalAveragePooling2D

Dense Layer: 512 units, ReLU activation

Dropout: 0.3 (reduces overfitting)

Dense Layer: 512 units, ReLU activation

Dropout: 0.3

Output Layer: Dense, 4 units (one per class), softmax activation

<img width="886" height="410" alt="image" src="https://github.com/user-attachments/assets/128ffe1a-a5b4-4c79-b3e7-dac0e8833bd2" />


Trainable params: 1,313,796 (≈5MB)

Non-trainable params: 23,587,712 (≈90MB)

Compilation Settings
Loss Function: categorical_crossentropy (for one-hot encoded multi-class)

Optimizer: Adam

Metrics: accuracy

Purpose:
This architecture uses ResNet50 as a feature extractor. Only the newly added dense layers (top classifier) and batch normalization/dropout layers are updated during training. The model is tailored for multi-class brain tumor MRI classification with 4 categories: glioma tumor, meningioma tumor, no tumor, and pituitary tumor
