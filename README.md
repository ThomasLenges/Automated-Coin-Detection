# Finding and Labelling Coins in an Image

## Project Overview

This project focuses on detecting and labeling coins in images using image processing and machine learning techniques. The workflow includes preprocessing images, applying segmentation techniques, and training a neural network for classification.

## Dataset (belonging to Signal Processing Laboratory 5. at EPFL) 

The dataset consists of a diverse set of images containing Euro, Swiss Franc and diverse coins in various denominations, lighting conditions, and backgrounds. Images may include different coin arrangements, occlusions, and other challenges commonly encountered in real-world scenarios. The dataset is split into training and testing sets, with corresponding annotations for model evaluation.

Regarding the background settings, neutral, noisy and hand means the coins are laid down on a uniform background, laid down on a noisy background, and held in hand, respectively. 

## Approach

### Intuition

To determine the most effective color spaces for coin detection, we analyzed the BGR, HSV, and LAB color spaces for sample images.

### Segmentation

- We identified different picture types (neutral\_bg, noisy\_bg, hand) based on the hue component (H) of the HSV color space.
- A threshold-based method was applied to classify image types before segmentation.
- The Hough Circle Transform was used to detect circular shapes representing coins in images. The radius parameters were adjusted based on reference images.
- Overlapping circles were merged using a function that computes their average.

### Model Training

- A **ResNet18** model was trained using **PyTorch**.
- The dataset was split into training and validation sets.
- The model was optimized using the Adam optimizer and evaluated using the **F1-score**.

## Authors

- **Paul Lanfermann** ([paul.lanfermann@epfl.ch](mailto\:paul.lanfermann@epfl.ch))
- **Thomas Lenges** ([thomaslenges@hotmail.com](mailto\:thomaslenges@hotmail.com))

