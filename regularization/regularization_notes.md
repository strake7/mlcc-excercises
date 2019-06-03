# Regularization

When you overfit to the data in the training set you may have greater loss when running on the validation data due to peculiarities in the training set. To prevent overfitting we penalize complex models, a principle called regularization.

Structural risk minimization = `minimize(Loss(Data|Model) + rate*complexity(Model))`

Model complexity: 
- a function of the weights of all the features in the model (L2 regularization). A feature weight with a high absolute value is more complex than a feature weight with a low absolute value
- a function of the total number of features with nonzero weights (later module)

L2 regularization: regularization is the sum of the squares of all the feature weights. Higher weights will significantly increase complexity. 
- Encourages weight values toward 0 (but not exactly 0)
- Encourages the mean of the weights toward 0, with a normal (bell-shaped or Gaussian) distribution.

## Regularization Rate: Lambda
Tunes the overall impact of the regularization term by multiplying its value by a scalar known 

Choosing a lambda value: the goal is to strike the right balance between simplicity and training-data fit:
- If your lambda value is too high, your model will be simple, but you run the risk of underfitting your data. Your model won't learn enough about the training data to make useful predictions.
- If your lambda value is too low, your model will be more complex, and you run the risk of overfitting your data. Your model will learn too much about the particularities of the training data, and won't be able to generalize to new data.
