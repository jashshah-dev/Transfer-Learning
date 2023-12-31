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

```
# Image Classification: Transfer Learning vs. CNN from Scratch

## Inferences

### Accuracy Comparison

The transfer learning model using MobileNet achieves an accuracy of 0.74, while the CNN model built from scratch has a lower accuracy of 0.65. This indicates that MobileNet performs better in terms of overall correctness in predictions.

### Precision, Recall, F1-Score

#### MobileNet
- Precision for class 0: 0.74
- Recall for class 0: 1.00
- F1-score for class 0: 0.85

#### CNN from Scratch
- Precision, recall, and F1-score for class 0 are lower compared to MobileNet (0.79, 0.80, 0.80, respectively).
- Overall lower values for precision, recall, and F1-score across classes.

### Macro and Weighted Averages

MobileNet exhibits higher macro and weighted averages for precision, recall, and F1-score compared to the CNN from scratch. This indicates better performance across all classes, taking into account class imbalances.

### Understanding Misclassifications

The CNN from scratch shows significant misclassifications, especially for class 1, where precision, recall, and F1-score are considerably lower. In contrast, MobileNet achieves better precision and recall for class 1.

### Class Imbalance Impact

The CNN from scratch struggles with the class imbalance, as seen in the lower precision, recall, and F1-score for class 1. MobileNet, having learned from a diverse set of classes during pre-training, demonstrates more balanced performance across classes.

### Generalization Ability

MobileNet achieves better accuracy and metrics across multiple classes, indicating superior generalization ability. The CNN from scratch, with a simpler architecture, faces challenges in capturing diverse features necessary for accurate predictions.

In summary, the higher accuracy, precision, recall, and F1-score of MobileNet compared to the CNN from scratch underscore the advantages of transfer learning in terms of leveraging pre-trained models and their ability to generalize to new tasks, especially when task-specific data is limited.

# Fine-Tuning DistilBERT for Text Classification

## Introduction

This repository provides a comprehensive guide on fine-tuning the DistilBERT model for text classification using TensorFlow and the Hugging Face Transformers library. Text classification is a common natural language processing (NLP) task, and DistilBERT, a distilled version of BERT (Bidirectional Encoder Representations from Transformers), offers a lightweight yet powerful solution.

## Getting Started

### Prerequisites

Ensure you have the following prerequisites installed:

- Python 3.6 or later
- TensorFlow
- Transformers library from Hugging Face
- Pandas
- Seaborn
- Matplotlib
- Plotly
- NLTK
- tqdm

You can install the required libraries using the following command:
```bash
pip install tensorflow transformers pandas seaborn matplotlib plotly nltk tqdm
```

## Dataset
This project assumes that you have a prepared dataset stored in the train_texts and test_texts variables. It is essential to ensure that your dataset is appropriately preprocessed and split into training and testing sets before proceeding with the model training.

## Tokenization
DistilBERT tokenization is a crucial step in preparing the data for training. The process is performed using the DistilBertTokenizer from the Hugging Face Transformers library. The tokenizer is initialized with a pre-trained DistilBERT model, specifically 'distilbert-base-uncased'. During tokenization, the training and testing texts are transformed into sequences of tokens, and the sequences are encoded with padding and truncation to align with the model's input requirements.

## Model Initialization
The base DistilBERT model for sequence classification is loaded using TFDistilBertForSequenceClassification from the Hugging Face Transformers library. Following the model initialization, it is compiled with an Adam optimizer and categorical cross-entropy loss, setting the stage for training.

## Custom Model Architecture
To enhance the base DistilBERT model, a custom neural network architecture named CustomDistilBERTModel is implemented. This architecture extends the base model by incorporating an additional dense layer with ReLU activation and an output layer with softmax activation. The extension allows for more flexibility and adaptability to specific text classification tasks.



