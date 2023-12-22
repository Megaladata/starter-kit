# ROC analysis

[Back to the list of components](../README.md)

## Purpose

Evaluating the quality of a model for estimating the probability of a certain event and calculating various metrics accepted in ROC analysis:

* calculation of sensitivity, specificity, and other ROC analysis indicators for each threshold value, specified with a given precision;
* calculation of the KS coefficient (Kolmogorov-Smirnov statistic);
* threshold selection using various methods.

## Input Ports

| Name            | Type        |
|:--------------------|:-----------|
| Input Dataset    | Table    |
| Algorithm parameters        | Variables |

### Structure of the table "Input dataset"

| Caption   | Type                                    | Description                                                               |
|:--------|:---------------------------------------|:-----------------------------------------------------------------------|
| Event | ![](./img/logical.svg) Logical      | **true** — corresponds to an event, **false** — corresponds to a non-event |
| CutOffPoint   | ![](./img/realnumber.svg) Float | Probability value of the event       |

### Variables in the "Algorithm parameters" port

| № | Caption                            | Type                                    | Value |
|:--|:---------------------------------|:---------------------------------------|:---------|
| 1 | Accuracy                         | ![](./img/integer.svg) Integer           |        4 |
| 2 | Sensitivity Bound         | ![](./img/realnumber.svg) Float |       90 |
| 3 | Misclassification Cost FP | ![](./img/realnumber.svg) Float |        1 |
| 4 | Misclassification Cost FN | ![](./img/realnumber.svg) Float |        1 |
| 5 | Threshold selection method    | ![](./img/string.svg) String        |        3 |

1. **Accuracy** — the number of decimal places to which the threshold value needs to be rounded.

2. **Sensitivity Bound** — the sensitivity level for threshold selection by the chosen method.

3. **Misclassification Cost FP**/**Misclassification Cost FN** — weights of the errors.

4.  **Threshold selection method**:

* Given sensitivity;
* Sensitivity equal to the event accuracy percentage;
* Maximum KS value;
* Minimum misclassification costs;
* Maximum event accuracy.

## Output ports

| Name              | Type        |
|:----------------------|:-----------|
| Dataset         | Table    |
| KS, %                 | Variables |
| Threshold       | Table    |

### Structure of the "Dataset" table

| Caption       | Type     | Description   |
|:------|:--------|:----------------------|
| Rounded Threshold                        | ![](./img/realnumber.svg) Float       | Threshold value rounded to a specified precision                                            |
| True Positives                      | ![](./img/integer.svg) Integer        | Number of True Positives (TP)                                                               |
| False Positives                    | ![](./img/integer.svg) Integer        | Number of False Positives (FP)                                                              |
| Predicted Positives                      | ![](./img/integer.svg) Integer        | TP + FP                                                                                     |
| True Negatives                      | ![](./img/integer.svg) Integer        | Number of True Negatives (TN)                                                               |
| False Negatives                     | ![](./img/integer.svg) Integer        | Number of False Negatives (FN)                                                              |
| Predicted Negatives                      | ![](./img/integer.svg) Integer        | TN + FN                                                                                     |
| Sensitivity %                           | ![](./img/realnumber.svg) Float       | ![\frac{TP}{(TP+FN)\cdot 100}](./img/7_roc.svg)                                             |
| Specificity %                           | ![](./img/realnumber.svg) Float       | ![\frac{TN}{(TN+FP)\cdot 100}](./img/8_roc.svg)                                             |
| (Percentage of events) - (Percentage of non-events) | ![](./img/realnumber.svg) Float      | ![(\frac{TP}{(TP+FN)\cdot 100}  - \frac{FP}{(TN+FP)\cdot 100})\cdot 100](./img/9_roc.svg)   |
| Change in True Positives                 | ![](./img/integer.svg) Integer        | Difference between the current and the next TP value                                        |
| Change in False Positives                | ![](./img/integer.svg) Integer        | Difference between the current and the next FP value                                        |
| ErrorRate %                                 | ![](./img/realnumber.svg) Float       | ![\frac{FP+FN}{(TP+FP+TN+FN)\cdot 100}](./img/10_roc.svg)                                   |
| FalsePositivesRate %                        | ![](./img/realnumber.svg) Float       | ![\frac{FP}{(TN+FP)\cdot 100}](./img/11_roc.svg)                                            |
| FalseNegativesRate %                         | ![](./img/realnumber.svg) Float       | ![\frac{FN}{(TP+FN)\cdot 100}](./img/12_roc.svg)                                            |
| Misclassification Costs                    | ![](./img/realnumber.svg) Float       | Errors weighed by their cost                                                                |
| Overall Classification Rate               | ![](./img/realnumber.svg) Float       | ![\frac{TP+TN}{(TP+TN+FP+FN)\cdot 100}](./img/13_roc.svg)                                   |
| Event Precision Rate                       | ![](./img/realnumber.svg) Float       | ![\frac{TP}{(TP+FP)\cdot 100}](./img/14_roc.svg)                                            |
| Non-event Precision Rate                   | ![](./img/realnumber.svg) Float       | ![\frac{TN}{(TN+FN)\cdot 100}](./img/15_roc.svg)                                            |

| № | Caption | Type                                    | Description                                  |
|:--|:----- |:---------------------------------------|:------------------------------------------|
| 1 | KS, % | ![](./img/realnumber.svg) Float | Kolmogorov-Smirnov statistic value  |

### Structure of the "Threshold Table Structure" table

| Caption                                     | Type                                      | Description                                                 |
|:-------------------------------------------|:-----------------------------------------|:------------------------------------------------------------|
| Threshold selection method                 | ![](./img/string.svg) String              | Name of the method                                           |
| Rounded threshold                          | ![](./img/realnumber.svg) Float           | Chosen threshold value, rounded to a given precision        |
| True positives                        | ![](./img/integer.svg) Integer            | Number of true positives (TP)                                |
| False positives                      | ![](./img/integer.svg) Integer            | Number of false positives (FP)                               |
| Predicted positives                        | ![](./img/integer.svg) Integer            | TP+FP                                                        |
| True negatives                       | ![](./img/integer.svg) Integer            | Number of true negatives (TN)                                |
| False negatives                      | ![](./img/integer.svg) Integer            | Number of false negatives (FN)                               |
| Predicted negatives                        | ![](./img/integer.svg) Integer            | TN+FN                                                        |
| Sensitivity, %                             | ![](./img/realnumber.svg) Float           | ![\frac{TP}{(TP+FN)\cdot 100}](./img/7_roc.svg)              |
| Specificity, %                             | ![](./img/realnumber.svg) Float           | ![\frac{TN}{(TN+FP)\cdot 100}](./img/8_roc.svg)              |
| (Percentage of events) - (Percentage of non-events)| ![](./img/realnumber.svg) Float           | ![(\frac{TP}{(TP+FN)\cdot 100}  - \frac{FP}{(TN+FP)\cdot 100})\cdot 100](./img/9_roc.svg)|
| Change in true positives                   | ![](./img/integer.svg) Integer            | Difference between current and next TP value                 |
| Change in false positives                  | ![](./img/integer.svg) Integer            | Difference between current and next FP value                 |
| ErrorRate %                                  | ![](./img/realnumber.svg) Float           | ![\frac{FP+FN}{(TP+FP+TN+FN)\cdot 100}](./img/10_roc.svg)    |
| False Positives Rate                          | ![](./img/realnumber.svg) Float           | ![\frac{FP}{(TN+FP)\cdot 100}](./img/11_roc.svg)             |
| False Negatives Rate                         | ![](./img/realnumber.svg) Float           | ![\frac{FN}{(TP+FN)\cdot 100}](./img/12_roc.svg)             |
| Misclassification Costs                       | ![](./img/realnumber.svg) Float           | Errors weighted by their cost                                |
| Overall Classification Rate                  | ![](./img/realnumber.svg) Float           | ![\frac{TP+TN}{(TP+TN+FP+FN)\cdot 100}](./img/13_roc.svg)    |
| Event Precision Rate %                           | ![](./img/realnumber.svg) Float           | ![\frac{TP}{(TP+FP)\cdot 100}](./img/14_roc.svg)             |
| No Event PrecisionRate %                       | ![](./img/realnumber.svg) Float           | ![\frac{TN}{(TN+FN)\cdot 100}](./img/15_roc.svg)             |