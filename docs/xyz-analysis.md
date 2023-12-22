# XYZ analysis

[Back to the list of components](../README.md)

## Purpose

The XYZ analysis allows classifying resources depending on the stability of their consumption based on the evaluation of the variation coefficients' values. In the component, objects are divided into three groups (X, Y, Z) according to the boundaries of the variation coefficient. The boundaries of the groups are set in variables.

## Input Ports

| Name             | Type        |
|:---------------------|:-----------|
| Input data set	 | Table    |
| Group boundaries	        | Variables |

### Structure of the "Input dataset" table

| Caption      | Type                                    | Description                                                                                         |
|:-----------|:---------------------------------------|:-------------------------------------------------------------------------------------------------|
| Object     | ![](./img/string.svg) String        | Identifier or name of the object being analyzed. For example, a product SKU  |
| Value | ![](./img/realnumber.svg) Float | Value of the indicator for the object. For instance, total sales amount           |
### Variables in the "Group Boundaries" Port

| № | Caption               | Type                                    | Value  |
|:--|:--------------------|:---------------------------------------|:----------|
| 1 | Group X Bound % | ![](./img/realnumber.svg) Float |        10 |
| 2 | Group Y Bound %| ![](./img/realnumber.svg) Float |        25 |

Group boundaries are set by the user. By default, the most commonly used boundaries are indicated.

## Output Ports

| Название   | Тип     |
|:-----------|:--------|
| XYZ groups | Table |

### Structure of the "XYZ Groups" table

| Caption                   | Type                                    | Description                                |
|:------------------------|:---------------------------------------|:----------------------------------------|
| Object                  | ![](./img/string.svg) String        |   Identifier or name of the object  |
| Group                  | ![](./img/string.svg) String        | Object's group identifier            |
| Variation % | ![](./img/realnumber.svg) Float | Variation coefficient value, %      |
| Average Value        | ![](./img/realnumber.svg) Float | Average indicator value for the object |
