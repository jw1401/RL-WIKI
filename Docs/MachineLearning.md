# Machine Learning

Machine learning (ML) is the scientific study of algorithms and statistical models that computer systems use to perform a specific task without using explicit instructions, relying on patterns and inference instead. It is seen as a subset of artificial intelligence. 

## Links

- [ML Crash Course](https://developers.google.com/machine-learning/crash-course/)

## Categories

- Supervised 
- Unsupervised
- [Reinforcement Learning](ReinforcementLearning.md) 

## Methods

- Classification and Regression (Linear, Logistics)
- Deep Learning with Neural Networks
- Support Vector Machines
- Random Forest
- K-Means (Unsupervised learning)
- Decision Trees
- Genetic Algorithms
- ...

## Libraries

- SCKIT
- Tensorflow
- KERAS
- PyTorch


# Algorithms

## Linear regression

For continuous linear predictions

A linear model is defined as 

    y = w * x + b

Mean Squared Error 

    MSE = 1/n * SUM(xi-x)² 

The goal is to minimize the Mean Squared Error to fit the Function to the dataset (Function approximation).
    
    Steps to take:
    
    - Take the derivative of MSE for calculating gradients 
    - Compute error/ gradients with training data (Supervised learning)
    - Backpropagate the gradients with Learning Rate lr by using gradient descent and adjust weights and bias (w, b)
    - Iterate until minimum is reached

After the training the model is used for making predictions (inference)

## Logistic regression

For classification tasks which uses a sigmoid function. Uses a similar compuational process as linear regression.

## Neural-Networks (nonlinear problems)

Neural networks introduces non linearities via an Activation Function for use in non linear problems (Classification and Regression) 

Equation of one Neuron:

    y = (w * x + b) + Activation-Function
    
Combine a number of neurons to create a Neural Network (MLP - Multi Layer Perceptron)

### Types

- Categorical Networks for Classification (uses Softmax to generate Probabilities)
- Continuous Networks for continuous outputs (Regression)


