# Trivial model

[Back to the list of components](../README.md)

## Purpose  

Building a Trivial (Base) Model for Event Probability Estimation. This component is used to build a simple model for estimating the probability of an event occurring based on a single input factor (continuous, integer, or real type). Logistic regression is employed with a prior optimal quantization procedure. The models are automatically retrained.

## Input Ports

| Name                  | Type       |
|:----------------------|:----------|
| Training dataset      | Table     |
| Test dataset          | Table     |

### Structure of "Training Dataset" and "Test Dataset" Tables

| Caption                | Type                                    | Description                        |
|:---------------------|:---------------------------------------|:-----------------------------------|
| ID           | ![](./img/string.svg) String            | Object identifier                  |
| Trivial field    | ![](./img/realnumber.svg) Float          | Field containing the trivial indicator |
| Event                | ![](./img/logical.svg) Logical          | Field containing the event        |

1. The field "Trivial Indicator" must be of continuous, real, or integer type.
2. The trivial field for both the test and training datasets should match, but this verification is the user's responsibility.
3. The "Event" field contains two unique logical values. `True` corresponds to the event occurrence.

## Output Ports

| Name                  | Type       |
|:----------------------|:----------|
| Event Probabilities  | Table     |
| Quality Metrics      | Variables |

## Algorithms

The logistic regression model estimates the probability of the event using the provided "Trivial Indicator."

For quality metrics, see the "Metrics" section of the output table.

### Structure of the "Event Probabilities" Table

| Caption                | Type                                    | Description                        |
|:---------------------|:---------------------------------------|:-----------------------------------|
| ID           | ![](./img/string.svg) String            | Object identifier                  |
| Event Probability    | ![](./img/realnumber.svg) Float          | Field containing the event probability |

Objects are sorted in descending order of event probability.

### Variables in the "Quality Metrics" Port

| № | Caption                          | Type                                    | Description                                         |
|:--|:-------------------------------|:---------------------------------------|:-----------------------------------------------------|
| 1 | AUC Value   | ![](./img/realnumber.svg) Float          | Calculated AUC score for the model                  |
| 2 | Quality    | ![](./img/string.svg) String            | Verbal description of the model's quality |
| 3 | Standard Error   | ![](./img/realnumber.svg) Float      | Standard error across the dataset                   |
| 4 | AUC Lower Confidence Interval      | ![](./img/realnumber.svg) Float    | Lower bound of the confidence interval              |
| 5 | AUC Upper Confidence Interval | ![](./img/realnumber.svg) Float    | Upper bound of the confidence interval              |
| 6 | Z-Estimate     | ![](./img/realnumber.svg) Float          | Calculated Z-score   |

The output port variables correspond to the [AUC component](./docs/auc.md) and are calculated for the test dataset. You can see the ROC curve diagrams for the test and training datasets by entering the component.
