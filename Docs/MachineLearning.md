# Machine Learning

## Categories

- Supervised 
- Unsupervised
- Reinforcement Learning

## Methods

- Linear Regression
- Logistics Regression
- Neural Networks (Deep Learning)
- Support Vector Machines
- Random Forest
- K-Means (Unsupervised)
- ...

## Libraries

- SCKIT
- Tensorflow
- KERAS
- PyTorch


# ML Algorithms

- Mean Squared Error
- Derivation (Auto Diff)
- Function Approximators

## Linear regression

For continuous linear predictions

A linear model is defined as y = w * x + d

Mean Squared Error (MSE) = 1/n * Summe(xi-x)² 
The goal is to minimize the MSE to fit the Function to the dataset.
    
    Steps to take:
    
    Derivative of MSE for calculating gradients 
    Error is backpropagated via gradient descent
    Make gradient descent iteration until minimum is reached

Coefficients w and d of line equation are fitted with training data [x,y] until mean squared error is minimized. The trained model is used for inference (predictions)

## Logistic regression

For classification tasks with sigmoid function. Same compuational process as linear regression.

## Neural-Networks (nonlinear problems)

linear + nonlinear  ⇒ (wx + b) + activation-function
mlp (multilayer perceptron) - fc (fully connected) layers
categorical (softmax networks with probabilities)
continuous (linear continous outputs)


