# Transfer-Learning

# Transfer Learning for Image Classification

This repository contains the implementation of transfer learning for large image classification using a MobileNet model. The goal is to fine-tune the model on a custom dataset with at least 3 classes, each having a minimum of 100 images.

## Dataset

- Collected images using a phone/camera, ensuring a diverse set of classes.
- Split the dataset into training, validation, and test sets.

## Data Preprocessing

- Built an input pipeline to preprocess and augment the training data.
- Implemented data augmentation techniques to enhance the model's robustness.

## Fine-tuning MobileNet

- Utilized the MobileNet model pre-trained on ImageNet.
- Fine-tuned the model on the custom dataset, adjusting the last layers for the new classification task.

## Results

### Classification Report

```plaintext
               precision    recall  f1-score   support
           0       0.79      0.80      0.80        80
           1       0.30      0.30      0.30        20
           2       0.00      0.00      0.00         8
    accuracy                           0.65       108
   macro avg       0.36      0.37      0.37       108
weighted avg       0.64      0.65      0.64       108
