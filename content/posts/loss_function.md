---
title: "Loss Functions"
date: 2023-10-23T21:45:29+11:00
draft: true
---

There are two main loss functions in deep learning, one for regression task and one for classification task. The loss functions are generally derived from maximum likelihood estimation (MLE).

1. **Mean Squared Error (MSE) Loss**:

   - **Task**: Regression
   - **Formula**:
     $$
     \text{MSE} = \frac{1}{N} \sum\_{i=1}^{N} (y_i - \hat{y}\_i)^2
     $$

   where $y_i$ is the true value, $\hat{y}_i$ is the predicted value, and $N$ is the number of samples.

   - **Description**: MSE computes the average squared difference between the actual and predicted values. The squaring ensures that larger errors have a disproportionately large impact, making the model more sensitive to outliers. This means that the model will try hard to fit those outliers, which can be a drawback in some situations.

2. **Cross-Entropy Loss (Log Loss)**:

   - **Task**: Classification
   - **Formula**:

     - **Binary Classification**:

     $$
     \text{Loss} = -\frac{1}{N} \sum_{i=1}^{N} [y_i \log(\hat{y}_i) + (1 - y_i) \log(1 - \hat{y}_i)]
     $$

     - **Multi-class Classification**:
       $$
       \text{Loss} = -\frac{1}{N} \sum_{i=1}^{N} \sum_{c=1}^{C} y_{ic} \log(\hat{y}_{ic})
       $$

   where $y_{ic}$ is the true label of class $c$ for sample $i$, $\hat{y}_{ic}$ is the predicted probability of class $c$ for sample $i$, $N$ is the number of samples, and $C$ is the number of classes.

   - **Description**: Cross-entropy measures the performance of a classification model whose output is a probability value between 0 and 1. The term "cross-entropy" arises from the field of information theory, and in the context of machine learning, it quantifies the difference between two probability distributions: the true distribution (given by the labels) and the estimated distribution (given by the model's predictions). A smaller value of cross-entropy indicates that the model's predictions are close to the true labels.
