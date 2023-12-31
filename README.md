# Bungaku Flower Classification Model using MobileNetV2

**Bungaku** is a mobile app designed to enrich knowledge about local flowers by providing flower identification and educational content for each recognized flower. The app utilizes advanced image recognition technology and an extensive botanical database to offer users a comprehensive learning experience.

## Overview

The script focuses on developing a flower classification model using a pre-trained MobileNetV2 architecture with TensorFlow and Keras. The workflow involves data preprocessing, model building, training, and conversion to TensorFlow Lite format.

## Data Preparation
- **Dataset:** [Flower Classification Dataset](https://www.kaggle.com/datasets/marquis03/flower-classification/code)
- Training and validation data directories are specified.
- Image dimensions are set to 224x224 pixels.
- Batch size for training is set to 32.
- `ImageDataGenerator` is used for data augmentation on the training set, including rescaling, shearing, zooming, and horizontal flipping.

## Data Generators

Data generators are created for training and validation using the specified directories, target size, batch size, and categorical class mode.

## Model Building

- MobileNetV2, pre-trained on ImageNet, is loaded as the base model.
- The base model layers are frozen to retain pre-trained weights.
- A Sequential model is built by adding:
  - Base model
  - GlobalAveragePooling2D layer
  - Dense layer with 128 units and ReLU activation
  - Dropout layer with a dropout rate of 0.5
  - Final Dense layer with 14 units (number of classes) and softmax activation.

## Model Compilation

The model is compiled with the Adam optimizer, categorical crossentropy loss, and accuracy as the metric.

## Model Training

- The model is trained using the `fit` method on the training generator.
- The number of epochs is set to 7.
- Validation data is provided to monitor model performance on unseen data.

## TensorFlow Lite Conversion

The trained model is converted to TensorFlow Lite format using the `TFLiteConverter`.
The converted model is saved to a .tflite file in the specified directory.

## Contributing

Feel free to contribute to the development of Bungaku API by submitting issues, suggesting improvements, or opening pull requests. We welcome your ideas and collaboration to make this project even better!
