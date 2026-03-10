# HandWrittenDigits

```markdown
# Handwritten Digit Classification using MLP Classifier (MNIST Dataset)

## Project Overview
This project demonstrates the classification of handwritten digits using a Multi-Layer Perceptron (MLP) Classifier on the popular MNIST dataset. The goal is to build a model that can accurately identify digits from 0 to 9 based on their pixel data.

## Dataset
The MNIST dataset is a large database of handwritten digits that is commonly used for training various image processing systems. It consists of 60,000 training images and 10,000 testing images. Each image is a 28x28 grayscale pixel array.

## Model
The model used for this classification task is an `MLPClassifier` from `sklearn.neural_network`. It's configured with two hidden layers of sizes (128, 64) neurons respectively, using the 'relu' activation function and the 'adam' solver.

## Key Steps
The notebook follows these steps:
1.  **Import Libraries**: Essential libraries like `numpy`, `matplotlib`, `sklearn.neural_network`, `sklearn.metrics`, and `tensorflow.keras.datasets` are imported.
2.  **Load Data**: The MNIST dataset is loaded directly using `mnist.load_data()`.
3.  **Flatten Images**: Each 28x28 pixel image is flattened into a 784-element vector to serve as input to the MLP.
4.  **Normalize Pixel Values**: Pixel values, originally in the range [0, 255], are normalized to [0, 1] for better model performance.
5.  **Initialize Model**: An `MLPClassifier` instance is created with specified hidden layer sizes, activation, solver, batch size, and a maximum of 5 iterations.
6.  **Train Model**: The model is trained on the preprocessed training data.
7.  **Predict**: Predictions are made on the test dataset.
8.  **Evaluate Model**: The model's performance is evaluated using a classification report and a confusion matrix.
9.  **Plot Sample Predictions**: A few sample test images are plotted along with their predicted labels to visually inspect the model's accuracy.
10. **Confusion Matrix**: The confusion matrix is displayed to provide a detailed breakdown of correct and incorrect classifications for each digit.

## Results
The model achieved a high accuracy:

### Classification Report:
```
              precision    recall  f1-score   support

           0       0.98      0.99      0.99       980
           1       0.99      0.99      0.99      1135
           2       0.96      0.98      0.97      1032
           3       0.96      0.98      0.97      1010
           4       0.97      0.98      0.98       982
           5       0.99      0.96      0.97       892
           6       0.98      0.98      0.98       958
           7       0.97      0.97      0.97      1028
           8       0.98      0.97      0.97       974
           9       0.98      0.95      0.96      1009

    accuracy                           0.98     10000
   macro avg       0.98      0.98      0.98     10000
weighted avg       0.98      0.98      0.98     10000
```

The accuracy of the model is approximately 98%.

### Confusion Matrix:
```
[[ 970    0    0    1    0    1    3    1    3    1]
 [   0 1123    5    1    0    1    3    1    1    0]
 [   4    1 1014    0    1    0    4    6    2    0]
 [   0    0    8  986    0    1    1    5    6    3]
 [   1    0    5    0  962    0    4    1    0    9]
 [   2    0    0   19    1  859    4    0    4    3]
 [   4    2    1    1    2    3  943    0    2    0]
 [   1    4   13    3    0    0    0 1002    1    4]
 [   3    0    6    6    5    3    0    5  944    2]
 [   2    7    1    9   16    3    0   11    5  955]]
```
The confusion matrix further confirms the model's strong performance, showing a high number of correct classifications along the diagonal.

## How to Run
1.  Ensure you have a Python environment with `numpy`, `matplotlib`, `scikit-learn`, and `tensorflow` installed.
2.  Open the `.ipynb` file in a Jupyter Notebook environment (e.g., Google Colab, Jupyter Lab).
3.  Run all cells sequentially.

## Potential Improvements
*   Increase `max_iter` for `MLPClassifier` to allow more training epochs and potentially improve convergence (as a ConvergenceWarning was noted).
*   Experiment with different network architectures (number of hidden layers, number of neurons per layer).
*   Try other activation functions.
*   Utilize Convolutional Neural Networks (CNNs) for potentially higher accuracy, as they are generally more suited for image data.
*   Implement data augmentation techniques.
```
