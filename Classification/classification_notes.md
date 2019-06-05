# Classification
Identify if a records is A or B (ex, spam, not spam)
Classification vs regression

How do you measure quality of models
    Accuracy: What percentage did we get right
    Precision - Cry wolf and was correct
    Recall - how many wolves did we get

## Thresholding
The value at which a classification is changed. Example: 0.6 probability we assume the email is spam

## True vs False & Positive vs Negative
Boy who cried wolf example:

- "Wolf" is a **positive** class.
- "No wolf" is a **negative** class.

**True positive** or **negative** is an outcome where the model **correctly** predicts the positive or negative class respectively

**False positive** or **negative** is an outcome where the model **incorrectly** predicts the positive or negative class respectively

## Accuracy
**Accuracy** = `# of correct predictions / total number of predictions`

Accuracy alone doesn't tell the full story when you're working with a class-imbalanced data set, like this one, where there is a significant disparity between the number of positive and negative labels.

## Precision and Recall 
**Precision**: What proportion of positive identifications was actually correct?
     = `TruePositives / TruePositives + FalsePositives`

**Recall**: What proportion of actual positives was identified correctly?
     = `TruePositives / TruePositives + FalseNegatives`

Precision and recall typically share an inverse relationship when the classification threshold is adjusted. That is, improving precision typically reduces recall and vice versa.

In general, a model that outperforms another model on both precision and recall is likely the better model.

## ROC Curve and AUC
**ROC curve** (receiver operating characteristic curve) is a graph showing the performance of a classification model at all classification thresholds. it plots two parameters:
- **True Positive Rate** - synonym for recall (`TruePositives / TruePositives + FalseNegatives`)
- **False Positive Rate** - `FalsePositives / FalsePositives + TrueNegatives`


ROC curve plots TPR vs. FPR at different classification thresholds. Lowering the classification threshold classifies more items as positive, thus increasing both False Positives and True Positives

![alt](https://developers.google.com/machine-learning/crash-course/images/ROCCurve.svg)

**AUC**: Area Under the ROC Curve

AUC measures the entire two-dimensional area underneath the entire ROC curve from (0,0) to (1,1). It provides a measure of performance across all possible classification thresholds. AUC is as the probability that the model ranks a random positive example more highly than a random negative example.

A model whose predictions are 100% wrong has an AUC of 0.0; one whose predictions are 100% correct has an AUC of 1.0
AUC is:
- Scale-invarient - it measure how well predictions are ranked rather than the absolute values
- Classification-threshold-invariant - It measures the quality of the model's predictions irrespective of what classification threshold is chosen

## Prediction Bias
**Prediction Bias**- measure how far apart two averages are = `average of predictions - average of labels in data set`.
Nonzero prediction bias tells you there is a bug somewhere in your model, as it indicates that the model is wrong about how frequently positive labels occur.

Possible root causes of prediction bias are:
- Incomplete feature set
- Noisy data set
- Buggy pipeline
- Biased training sample
- Overly strong regularization


