# ABC analysis (method of tangents)

[Back to the list of components](../README.md)

## Purpose

Similar to the [ABC-analysis](./abc-analysis.md) component, but the group boundaries are determined automatically using the tangent method. Subsequently, objects are divided into three groups (A, B, C) according to the calculated group boundaries.
## Input Ports

| Name             | Type     |
|:---------------------|:--------|
| Input data set | Table |

### Structure of the "Input dataset" table

| Caption      | Type  | Description         |
|:-----------|:-------|:-----------------------|
| Object     | ![](./img/string.svg) String        | Identifier or name of the object being analyzed. For example, a product SKU  |
| Value | ![](./img/realnumber.svg) Float | Value of the indicator for the object. For instance, total sales amount  |

## Output Ports

| Caption                     | Type        |
|:-----------------------------|:-----------|
| ABC groups and contributions of object | Table    |
| Group boundaries                | Variables |

### Structure of the "ABC Groups and Contributions of Objects" table

| Caption   | Type  | Description  |
|:-------------------------|:---|:-----------|
| Object | ![](./img/string.svg) String   | Identifier or name of the object|
| Value  | ![](./img/realnumber.svg) Float | Value of the indicator for the object  |
| Cumulative Impact | ![](./img/realnumber.svg) Float | Accumulative impact of objects    |
| Group    | ![](./img/string.svg) String        | Identifier of the object's group              |

### Variables in the "Group Boundaries" Port

| № | Caption    | Type  | Description  |
|:--|:--------------------|:---------|:---|
| 1 | Bound 1 %	 | ![](./img/realnumber.svg) Float | Calculated value of group 1 boundary. |
| 2 | Bound 2 %	 | ![](./img/realnumber.svg) Float | Calculated value of group 2 boundary. |