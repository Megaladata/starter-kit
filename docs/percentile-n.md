# N% Percentile

[Back to the list of components](../README.md)

## Purpose

This component calculates the value of the Nth percentile in a dataset. The percentile is expressed in percentages and indicates which value is below the specified percentage of data. For instance, speaking about the 75th percentile means that 75% of the values are lower than this value, and the remaining 25% are higher.

## Input Ports

| Name          | Type       |
|:--------------|:-----------|
| Data Series   | Table      |
| Variables     | Variables  |

### Structure of the "Data Series" Table

| Caption       | Type       | Description         |
|:------------|:----|:--------------------|
| Values      | ![](./img/realnumber.svg) Real Number    | Original data series |

### Variables in the "Variables" port

| № | Caption       | Type        | Value   |
|:--|:------------|:---------|:--------|
| 1 | Value N     | ![](./img/integer.svg) Integer      | 95      |
| 2 | Comparison  | ![](./img/string.svg) String       | >       |

The **Value N** variable represents the desired percentile value in percentages. The **Comparison** variable can take values `>` or `<`, influencing the logic for creating the output column **Flag**.

## Output Ports

| Name          | Type        |
|:--------------|:-----------|
| Data Series   | Table       |
| Percentile    | Variables   |
| Percentile    | Table       |

## Structure of the "Data Series" Table

| Caption       | Type                                     | Description         |
|:------------|:-----------------------------------------|:--------------------|
| Values      | ![](./img/realnumber.svg) Real Number    | Original data series|
| Flag        | ![](./img/logical.svg) Logical           | See below           |

The value in the **Flag** column is `True` if the series value is greater or less (depending on the **Comparison** variable) than the percentile.

### Variables in the "Percentile" port

| № | Caption       | Type                                     | Value                |
|:--|:------------|:-----------------------------------------|:---------------------|
| 1 | Percentile  | ![](./img/realnumber.svg) Real Number    | Calculated percentile|

## Structure of the "Percentile" Table

| Label       | Type       | Description             |
|:------------|:---------|:------------------|
| Percentile  | ![](./img/realnumber.svg) Real Number    | Calculated percentile   |
