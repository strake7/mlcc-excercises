# Feature Crosses
Feature cross - a synthetic feature that encodes nonlinearity in the feature space by multiplying two or more input features together
Examples:
- [A X B]: a feature cross formed by multiplying the values of two features.
- [A x B x C x D x E]: a feature cross formed by multiplying the values of five features.
- [A x A]: a feature cross formed by squaring a single feature.

## Crossing One-Hot Vectors
Examples:
`country=USA, country=France or language=English, language=Spanish` could be crossed as a logical conjunction ` country:usa AND language:spanish`.
Another common example is coordinates

```
 binned_latitude = [0, 0, 0, 1, 0]
 binned_longitude = [0, 1, 0, 0, 0]
```

This feature cross is a 25-element one-hot vector (24 zeroes and 1 one). The single 1 in the cross identifies a particular conjunction of latitude and longitude

## Why?
Enable a model to fit nonlinear data