# MNIST Handwritten Digit Recognition

## Project Overview

This project focuses on recognizing handwritten digits (0–9) using Machine Learning and Deep Learning techniques.

The MNIST dataset contains 70,000 grayscale images of handwritten digits. Each image has a resolution of 28 × 28 pixels.

Five classification models were implemented and evaluated to compare their performance. The main objective was to identify the most effective model for handwritten digit recognition.

## Project Objectives

- Load and explore the MNIST dataset.
- Perform Exploratory Data Analysis (EDA).
- Preprocess and normalize image data.
- Implement and compare different Machine Learning and Deep Learning models.
- Evaluate model performance using classification metrics.
- Analyze CNN prediction errors.
- Experiment with CNN architecture improvements.

## Dataset Description

The project uses the MNIST handwritten digits dataset.

| Dataset | Number of Images |
| Training set | 60,000 |
| Test set | 10,000 |
| Total | 70,000 |

**Image properties:**
- Image size: 28 × 28 pixels
- Color mode: Grayscale
- Number of classes: 10 (digits 0–9)
- Pixel intensity range: 0–255

The dataset was obtained from Kaggle and stored in the `data/raw/` directory.

## Data Preprocessing

The following preprocessing steps were performed:

- Loading image and label data from IDX binary files.
- Reshaping images into 784-dimensional feature vectors for classical Machine Learning models.
- Normalizing pixel values to the range [0, 1].
- Preparing images in the shape of 28 × 28 × 1 for CNN.
- Splitting the original training data into training and validation sets.

The validation split contains 54,000 training images and 6,000 validation images.

The original test set (10,000 images) was kept separate for final model evaluation.

## Models Implemented

Five classification models were developed:

1. **Logistic Regression** – A linear classification model used as a baseline.
2. **K-Nearest Neighbors (KNN)** – A distance-based classification algorithm.
3. **Random Forest** – An ensemble learning method based on decision trees.
4. **Artificial Neural Network (ANN)** – A fully connected neural network.
5. **Convolutional Neural Network (CNN)** – A deep learning model designed to learn spatial features from images.

## Model Performance

All models were evaluated on the same held-out test dataset containing 10,000 images.

| Model | Accuracy |
| CNN | 98.99% |
| ANN | 97.62% |
| KNN | 97.09% |
| Random Forest | 96.96% |
| Logistic Regression | 92.43% |

**Best Performing Model: CNN**

The CNN achieved the highest test accuracy of **98.99%**, correctly classifying 9,899 out of 10,000 test images.

## Evaluation Metrics

The following metrics were used to evaluate model performance:

- Accuracy
- Precision
- Recall
- F1-Score
- Confusion Matrix

Classification reports and confusion matrices were generated to provide a more detailed evaluation of each model.

## CNN Error Analysis

A detailed error analysis was performed on the CNN predictions.

Key findings:

- 9,899 test images were classified correctly.
- 101 test images were misclassified.
- Misclassification patterns were analyzed by comparing actual and predicted labels.
- Model confidence scores were examined for correct and incorrect predictions.
- Digit-level performance was evaluated using Precision, Recall, and F1-Score.

The analysis also showed that some incorrect predictions had relatively high confidence scores.

## CNN Improvement Experiments

Two additional CNN experiments were conducted:

**1. Data Augmentation**

Random rotation, translation, and zoom transformations were applied during training.

**2. Improved CNN Architecture**

An alternative architecture using additional convolutional layers and Batch Normalization was evaluated.

The original CNN baseline achieved the best validation performance among the three CNN configurations. Therefore, it was retained as the final model.

## Project Structure

```text
MNIST_Digit_Recognition/
│
├── data/
│   └── raw/
│       ├── train-images.idx3-ubyte
│       ├── train-labels.idx1-ubyte
│       ├── t10k-images.idx3-ubyte
│       └── t10k-labels.idx1-ubyte
│
├── models/
│   ├── logistic_regression.pkl
│   ├── knn_model.pkl
│   ├── random_forest.pkl
│   ├── ann_model.keras
│   ├── cnn_model.keras
│   ├── cnn_baseline.keras
│   ├── augmented_cnn.keras
│   └── improved_cnn.keras
│
├── outputs/
│   ├── figures/
│   ├── reports/
│   └── results/
│
├── notebooks/
│   └── Data_Exploration.ipynb
│
├── README.md
└── requirements.txt
```

## Technologies and Libraries

- Python
- NumPy
- Pandas
- Matplotlib
- Seaborn
- Scikit-learn
- TensorFlow / Keras
- Joblib
- Jupyter Notebook

## Installation

Clone the repository:

```bash
git https://github.com/zahranaimie/MNIST_Digit_Recognition
```

Navigate to the project directory:

```bash
cd MNIST_Digit_Recognition
```

Install the required libraries:

```bash
pip install -r requirements.txt
```

Make sure the MNIST IDX files are placed inside `data/raw/` before running the notebook.

## How to Run

1. Open the project directory in Jupyter Notebook.
2. Open the main project notebook.
3. Run the notebook cells in order.
4. The generated figures, reports, and model results will be saved in the `outputs/` directory.
5. Trained models will be saved in the `models/` directory.

## Conclusion

This project demonstrates the application of Machine Learning and Deep Learning techniques to handwritten digit recognition.

Among the five implemented models, the Convolutional Neural Network achieved the best performance, with a test accuracy of 98.99%.

The project provided practical experience in data loading, preprocessing, exploratory data analysis, model development, performance evaluation, error analysis, and neural network experimentation.

## Future Improvements

- Develop a simple web application for interactive digit recognition.
- Test the model on handwritten digits outside the MNIST dataset.
- Explore additional CNN architectures and hyperparameter configurations.
- Improve model interpretability using visualization techniques.

## Author

**Zahra Naimie Nosaleh**

Machine Learning and Deep Learning Project