Comparative analysis of ANN,DEEP BPN and CNN for MNIST digit recognition

Project Overview

This project implements and compares three neural network architectures for handwritten digit classification using the MNIST dataset. The goal is to analyze how model complexity affects performance in image classification tasks.

The models implemented are:
	•	Single Hidden Layer Backpropagation Neural Network (BPN)
	•	Multi Hidden Layer Backpropagation Neural Network
	•	Convolutional Neural Network (CNN)

The project includes data preprocessing, model training, and evaluation using multiple performance metrics.


Dataset

The dataset used in this project is the MNIST (Modified National Institute of Standards and Technology) dataset, which contains handwritten digit images.

Dataset Characteristics
	•	Total Images: 70,000
	•	Training Images: 60,000
	•	Testing Images: 10,000
	•	Image Size: 28 × 28 pixels
	•	Number of Classes: 10 (digits 0–9)
	•	Image Type: Grayscale

The dataset is loaded directly from TensorFlow/Keras.


Data Preprocessing

The following preprocessing steps were applied:
	1.	Dataset Loading
	•	Loaded MNIST dataset using TensorFlow Keras.
	2.	Normalization
	•	Pixel values were scaled from the range 0–255 to 0–1 to improve model training.
	3.	Reshaping for CNN
	•	Images were reshaped from
(28, 28) → (28, 28, 1)
to include a channel dimension for convolution operations.


Models Implemented

1. Single Hidden Layer BPN (ANN)

Architecture:

Input Layer
→ Flatten (784 features)
→ Dense Layer (128 neurons, ReLU activation)
→ Output Layer (10 neurons, Softmax activation)

Optimizer: Adam
Loss Function: Sparse Categorical Crossentropy
Metric: Accuracy


2. Multi Hidden Layer BPN

Architecture:

Input Layer
→ Flatten
→ Dense (256 neurons, ReLU)
→ Dense (128 neurons, ReLU)
→ Dense (64 neurons, ReLU)
→ Output Layer (10 neurons, Softmax)

Optimizer: Adam
Loss Function: Sparse Categorical Crossentropy
Metric: Accuracy

This architecture allows the network to learn more complex feature representations compared to the single hidden layer model.


3. Convolutional Neural Network (CNN)

Architecture:

Input (28×28×1)
→ Conv2D (32 filters, 3×3 kernel, ReLU)
→ MaxPooling (2×2)
→ Conv2D (64 filters, 3×3 kernel, ReLU)
→ MaxPooling (2×2)
→ Flatten
→ Dense (128 neurons, ReLU)
→ Output Layer (10 neurons, Softmax)

CNN preserves spatial relationships in the image and is highly effective for image-based tasks.


Model Training

All models were trained using:
	•	Epochs: 5
	•	Batch Size: 128 (for deeper models)
	•	Optimizer: Adam


Evaluation Metrics

Each model was evaluated using the following metrics:
	•	Accuracy
	•	Loss
	•	Precision
	•	Recall
	•	F1 Score
	•	Confusion Matrix

The classification report and confusion matrix help analyze how well the model predicts each digit class.
