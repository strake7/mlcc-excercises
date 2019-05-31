# Representation

Feature engineering - transforming raw data into a feature vector.

## Categorical features
Categorical features have a discrete set of possible values. Fixed class categories

To use these features map the string representation to an vector. Ex [0,0,0,1,0] = "Yoga"
The length of this vector is equal to the number of elements in the vocabulary. This representation is called a one-hot encoding when a single value is 1, and a multi-hot encoding when multiple values are 1.
![alt](https://developers.google.com/machine-learning/crash-course/images/OneHotEncoding.svg)

### Sparse Representation
For non-fixed sets such as 1 million different street names use [sparse representation](https://developers.google.com/machine-learning/glossary/#sparse_representation) in which we store on nonzero values.


## Qualities of good features
Properties of a good feature 
- should occur a handful of times in the dataset with a non-zero value. Avoid rarely used discrete feature values. 
- should have a clear and obvious meaning
- should not take on magic values. Don't mix "magic" values with actual data. Use a boolean in a separate field to indicate that the value is defined or not
- should not change over time
- should not have crazy outliers

Using binning to segment groups into u


Know your data - use histograms, scatter charts to visualize outliers


## Cleaning Data
### Scaling
Convert floating-point feature values from their natural range(for example, 100 to 900) into a standard range (for example, 0 to 1 or -1 to +1)

Provides the following benefits:
- Helps gradient descent converge more quickly
- Avoid NaN trap when a value exceed floating point precision limit 
- Lessen attention to features having a wider range
#### How?
- Linearly map [min value, max value] to a small scale, such as [-1, +1]
- Calculate the Z score of each value `scaled value= (value-mean)/stdev`


### Eliminate Outliers

Check the distribution of features for long tails.

![alt](https://developers.google.com/machine-learning/crash-course/images/ScalingNoticingOutliers.svg)

#### How to eliminate?
- Take the logarithmic of the feature. Check distribution againagain
- Cap the maximum value. Clipping the feature value at 4.0 doesn't mean that we ignore all values greater than 4.0. Rather, it means that all values that were greater than 4.0 now become 4.0.


### Binning

Divide possible value ranges into assignable bins so that we can set it in a vector (ex. every 10 degrees of latitude). Similar to one-hot encoding:
[0, 0, 0, 0, 0, 1, 0, 0, 0, 0, 0]


### Scrubbing
Remove records with bad data:

- Omitted values. For instance, a person forgot to enter a value for a house's age.
- Duplicate examples. For example, a server mistakenly uploaded the same logs twice.
- Bad labels. For instance, a person mislabeled a picture of an oak tree as a maple.
- Bad feature values. For example, someone typed in an extra digit, or a thermometer was left out in the sun.

Histograms are a great mechanism for visualizing your data in the aggregate. In addition, getting statistics like the following can help:

- Maximum and minimum
- Mean and median
- Standard deviation

Create lists of discrete features you expect and find if the distribution of data for those values matches your expectation.

Good ML relies on good data.

### Develop a Good Feature Set
A correlation matrix shows pairwise correlations, both for each feature compared to the target and for each feature compared to other features.
Correlation values have the following meanings:

- -1.0: perfect negative correlation
- 0.0: no correlation
- 1.0: perfect positive correlation

Features that have strong positive or negative correlations with the target will add information to our model.
We'd also like to have features that aren't so strongly correlated with each other, so that they add independent information.
Use this information to try removing features. You can also try developing additional synthetic features, such as ratios of two raw features.

Correlation of features and targets: 
```
correlation_dataframe = training_examples.copy()
correlation_dataframe["target"] = training_targets["median_house_value"]

correlation_dataframe.corr()
```
Scatter plot of feature correlation: ```plt.scatter(training_examples["latitude"], training_targets["median_house_value"])```
