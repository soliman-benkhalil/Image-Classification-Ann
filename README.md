# Malaria Cell Image Classification using Neural Networks

This project compares two approaches for classifying malaria cell images: a deep neural network with raw image input and a neural network with HOG (Histogram of Oriented Gradients) feature extraction.

## Table of Contents
- [Approaches](#approaches)
  - [Deep Neural Network with Raw Images](#1-deep-neural-network-with-raw-images)
  - [Neural Network with HOG Feature Extraction](#2-neural-network-with-hog-feature-extraction)
- [Key Findings](#key-findings)
- [Evaluation Methods](#evaluation-methods)
- [Conclusion](#conclusion)

## Approaches

### 1. Deep Neural Network with Raw Images

- **Input**: Raw images resized to 64x64 pixels
- **Preprocessing**: Normalization (pixel values divided by 255)
- **Architecture**: 
  - Input layer: 12,288 neurons (64 * 64 * 3)
  - 10 hidden layers with sizes: 256, 128, 64, 32, 16, 8, 4, 2 neurons
  - Output layer: 2 neurons (softmax activation)
- **Regularization**: L2 regularization, Batch Normalization, Dropout

### 2. Neural Network with HOG Feature Extraction

- **Input**: HOG features extracted from 64x64 pixel images
- **Preprocessing**: HOG feature extraction (inherently includes normalization)
- **Architecture**:
  - Input layer: Size depends on HOG feature vector
  - 2 hidden layers with 64 and 32 neurons
  - Output layer: 2 neurons (softmax activation)
- **Regularization**: L2 regularization, Dropout

## Key Findings

1. **Feature Extraction Impact**: HOG feature extraction significantly improved model performance and reduced the need for a complex architecture.
2. **Model Complexity**: The raw image model required a deeper architecture with more regularization techniques to achieve comparable results.
3. **Preprocessing**: The HOG-based model inherently handled normalization and flattening through feature extraction, simplifying the preprocessing pipeline.
4. **Accuracy Improvement**: Despite the simpler architecture, the model with HOG feature extraction achieved better accuracy compared to the complex architecture using raw images.
5. **Deep Learning Clarification**: Both models are considered deep neural networks due to their multiple hidden layers. The term "deep" refers to the network's architecture (multiple hidden layers) rather than its ability to perform automatic feature extraction. Therefore, even the ANN working on raw image data is a deep neural network, despite not performing automatic feature extraction like a CNN would.

## Evaluation Methods

Both models were evaluated using:
- Training and validation loss curves
- ROC (Receiver Operating Characteristic) curve
- Confusion matrix

These evaluation methods provided comprehensive insights into model performance, helping to validate the superiority of the feature extraction approach.

## Conclusion

Feature extraction using HOG proved to be a powerful technique for this classification task, allowing for a simpler model architecture while achieving higher accuracy. This approach demonstrates the importance of thoughtful feature engineering in machine learning projects, often outperforming more complex models that work directly with raw data. Moreover, this project highlights that deep learning isn't just about automatic feature extraction, but can also benefit from well-designed manual feature extraction techniques.
