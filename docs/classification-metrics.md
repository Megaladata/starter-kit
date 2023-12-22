# Classification metrics

[Back to the list of components](../README.md)

## Purpose

Allows calculating a series of metrics for evaluating classification quality.

### Input Ports

| Name                 | Type       |
|:---------------------|:---------- |
| Dataset   | Table      |

### Structure of the "Dataset" Table

| Caption                  | Type                                | Description                       |
|:-----------------------|:-----------------------------------|:----------------------------------|
| Event is True            | ![](./img/integer.svg) Integer     | True event value: 1 — event occurred; 0 — event did not occur      |
| Event is Predicted       | ![](./img/integer.svg) Integer     | Predicted event value: 1 — model predicted event occurred; 0 — model predicted event did not occur    |

## Output Ports

| Name            | Type           |
|:----------------|:---------------|
| Metrics         | Variables      |

### Variables in the "Metrics" Port

| # | Caption              | Type                                    | Description                           |
|:-:|:-------------------|:---------------------------------------|:--------------------------------------|
| 1 | Precision          | ![](./img/realnumber.svg) Float         | see **Algorithms**                   |
| 2 | Recall             | ![](./img/realnumber.svg) Float         | see **Algorithms**                   |
| 3 | F1 Score           | ![](./img/realnumber.svg) Float         | see **Algorithms**                   |
| 4 | Accuracy           | ![](./img/realnumber.svg) Float         | see **Algorithms**                   |
| 5 | True Negative (TN) | ![](./img/integer.svg) Integer         | Number of true negative cases        |
| 6 | False Positive (FP)| ![](./img/integer.svg) Integer         | Number of false positive cases       |
| 7 | False Negative (FN)| ![](./img/integer.svg) Integer         | Number of false negative cases       |
| 8 | True Positive (TP) | ![](./img/integer.svg) Integer         | Number of true positive cases        |

## Algorithms

Precision = TP / (TP + FP)

Recall = TP / (TP + FN)

F1 Score = 2 * (Precision * Recall) / (Precision + Recall)

Accuracy = (TN + TP) / (TN + FP + FN + TP)


1. [F-score](https://en.wikipedia.org/wiki/F-score)