# ABC analysis

[Back to the list of components](../README.md)

## Purpose

The component implements a method that allows classifying resources by their importance based on the Pareto principle. Objects are divided into three groups (A, B, C) according to the boundaries of the groups. The boundaries of the groups are set in variables.
## Input Ports

| Name             | Type        |
|:---------------------|:-----------|
| Input data set | Table    |
| Group boundaries        | Variables |

### Structure of the "Input dataset" table

| Caption      | Type     | Description   |
|:-----------|:-------|:-----------------|
| Object     | ![](./img/string.svg) String        | Identifier or name of the object being analyzed. For example, a product SKU  |
| Value | ![](./img/realnumber.svg) Float | Value of the indicator for the object. For instance, total sales amount           |

### Variables in the "Group Boundaries" Port

| № | Caption               | Type                                    | Value  |
|:--|:--------------------|:---------------------------------------|:----------|
| 1 | Bound 1 %	 | ![](./img/realnumber.svg) Float |        80 |
| 2 | Bound 2 %| ![](./img/realnumber.svg) Float |        95 |

Group boundaries are set by the user. By default, the most commonly used boundaries are indicated.

## Output Ports

| Caption                     | Type     |
|:-----------------------------|:--------|
| ABC groups and contributions of objects | Table |

### Structure of the "ABC Groups and Contributions of Objects" table

| Caption  | Type   | Description  |
|:-------------------------|:--------|:----|
| Object                   | ![](./img/string.svg) String        | Identifier or name of the object   |
| Value               | ![](./img/realnumber.svg) Float | Value of the indicator for the object          |
| Cumulative Impact | ![](./img/realnumber.svg) Float | Accumulative impact of objects             |
| Group                   | ![](./img/string.svg) String        | Identifier of the object's group             |

## Algorithms

* [ABC analysis](https://en.wikipedia.org/wiki/ABC_analysis)