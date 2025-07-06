# Dog Breed Identification – Major Assignment 2

This project tackles the Kaggle "Dog Breed Identification" challenge using Convolutional Neural Networks with transfer learning. The goal is to classify dog images into one of 120 breeds.

## Model Architecture

- **Base Model:** MobileNetV2 (`imagenet` weights, `include_top=False`)
- **Input Size:** 224x224x3
- **Custom Head:**
  - GlobalAveragePooling2D
  - Dropout (rate = 0.3)
  - Dense layer with 120 units and `softmax` activation

The base model was frozen initially and then fine-tuned after training the top layers.

## Transfer Learning Strategy

- Loaded `MobileNetV2` without top classification layers and froze all base layers.
- Trained the custom top layers for 10 epochs.
- Then unfroze the entire base model and fine-tuned the network for 5 additional epochs using a lower learning rate (`1e-5`).

## Performance Metrics

- **Top Accuracy Achieved:** ~94.2% on training set (after fine-tuning)
- **Validation Accuracy:** ~73.9%
- **Validation Loss:** ~0.88

Metrics were monitored using `categorical_crossentropy` loss and `accuracy`.

## Instructions to Load the Saved Model

To load and use the trained model for inference:

```python
from tensorflow.keras.models import load_model

# Load model from saved path
model = load_model('/content/drive/MyDrive/dog_breed_data/cnn_model.h5')

## Files Included

| File Name             | Description                                           |
|-----------------------|-------------------------------------------------------|
| `dog_breed_MA2.ipynb` | Complete Jupyter notebook with training and inference |
| `cnn_model.h5`        | Trained Keras model saved in HDF5 format              |
| `submission.csv`      | Predictions submission                                |
