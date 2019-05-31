# Training, Validation and Test Sets
**Training set** — a subset to train a model.

**Test set** — a subset to test the trained model.

The two partition approach the workflow to train a model could look as follows:
![FLAWED](https://developers.google.com/machine-learning/crash-course/images/WorkflowWithTestSet.svg)
The issue with this approach is that it is implicitly overfit to the peculiarities of the test set.

**Training set** - another subset of data to evaluate the trained model. Use the validation set to evaluate results from the training set. Then, use the test set to double-check your evaluation after the model has "passed" the validation set. The following figure shows this new workflow:
    Pick the model that does best on the validation set.
    Double-check that model against the test set.

   ![BETTER](https://developers.google.com/machine-learning/crash-course/images/WorkflowWithValidationSet.svg)

When checking the validity of your training and validation sets the distribution of values between the train and validation splits should be roughly equal. Use scatter plot to check for large differences in data distribution. Also be sure to reindex the dataset before pulling subsets to avoid any inherited sorting. `df.reindex(
  np.random.permutation(df.index)`