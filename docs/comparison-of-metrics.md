# Metrics comparison

[Back to the list of components](../README.md)

## Purpose

Component for Comparing Current Metrics with Reference Scale AUC, Gini, KS, Silhouette Index, and Custom Scale with Visualization

### Input Ports

| Name           | Type       |
|:---------------|:---------- |
| Metric 1       | Variables  |
| Metric 2       | Variables  |
| Metric 3       | Variables  |
| Type of metrics    | Variables  |

#### Variables in "Metric 1" Port

| # | Caption                 | Type                                   | Value              |
|:-:|:----------------------|:---------------------------------------|:-------------------|
| 1 | Metric 1 Label        | ![](./img/string.svg) String           | Training set       |
| 2 | Metric 1 Value        | ![](./img/realnumber.svg) Float         | 0.6                |

#### Variables in "Metric 2" Port

| # | Caption                 | Type                                   | Value              |
|:-:|:----------------------|:---------------------------------------|:-------------------|
| 1 | Metric 2 Label        | ![](./img/string.svg) String           | Test set           |
| 2 | Metric 2 Value        | ![](./img/realnumber.svg) Float         | 0.7                |

#### Variables in "Metric 3" Port

| # | Caption                 | Type                                   | Value              |
|:-:|:----------------------|:---------------------------------------|:-------------------|
| 1 | Metric 3 Label        | ![](./img/string.svg) String           | null               |
| 2 | Metric 3 Value        | ![](./img/realnumber.svg) Float         | null               |

### Variables in "Metric Type" Port

| # | Caption  | Type  | Value      |
|:-:|:---------------------|:-------------------|:---------- |
| 1 | Metrics Type          | ![](./img/string.svg) String         | Custom     |
| 2 |Unsatisfactory       | ![](./img/realnumber.svg) Float       | 0.30       |
| 3 |Average              | ![](./img/realnumber.svg) Float       | 0.50       |
| 4 |Good                 | ![](./img/realnumber.svg) Float       | 0.70       |
| 5 |Very Good            | ![](./img/realnumber.svg) Float       | 0.90       |
| 6 |Excellent            | ![](./img/realnumber.svg) Float       | 0.99       |

**Metric Type** - allows you to choose the scale type for comparing metrics. Possible values:

* **AUC** - AUC index;
* **Gini** - Gini index;
* **KS** - KS statistic;
* **SI** - Silhouette index;
* **Custom** - custom scale (default).

### Output Ports

| Name             | Type       |
|:-----------------|:---------- |
| Metric Comparison| Table      |

### Structure of "Comparison of metrics" Table

| Caption                | Type                               | Description                                      |
|:---------------------|:-----------------------------------|:--------------------------------------------------|
| Metric Type          | ![](./img/string.svg) String       | Name of the reference scale and labels of current metrics |
| Current              | ![](./img/realnumber.svg) Float     | Values of current metrics                        |
| Unsatisfactory       | ![](./img/realnumber.svg) Float     | Unsatisfactory value of the reference scale      |
| Average              | ![](./img/realnumber.svg) Float     | Average value of the reference scale             |
| Good                 | ![](./img/realnumber.svg) Float     | Good value of the reference scale                |
| Very Good            | ![](./img/realnumber.svg) Float     | Very good value of the reference scale           |
| Excellent            | ![](./img/realnumber.svg) Float     | Excellent value of the reference scale           |

## Visualizations

### "Metric Comparison" Diagram

![](./img/1_comparison-of-clustering.svg)