# Row splitter (Variables)

[Back to the list of components](../README.md)

## Purpose

Allows splitting a variable's value, recorded with delimiters, into multiple rows. Only one delimiter is considered (specified in the variable). The output results in a dynamic number of rows. The component's string parsing algorithm is analogous to the **Row splitter** component.

## Input Ports

| Name             | Type        |
|:---------------------|:-----------|
| Variables    | Variables |

### Structure of the table "Input Dataset"

| Caption          | Type   | Description       |
|:---------------|:------------|:--------------------------|
| Input String | ![](./img/string.svg) String | String with delimiters, the values of which need to be split into different rows |

### Variables in the "Variables" port

| Caption          | Type                             | Value    |
|:---------------|:--------------------------------|:------------|
| Input String | ![](./img/string.svg) String | null        |
| Delimiter    | ![](./img/string.svg) String | ,           |

**Delimiter** - Specifies the delimiter present in the input string. Based on this, parts of the string and their number are determined.

## Output Tables

| Caption     | Type     |
|:-------------|:--------|
| Dataset | Table |

### Structure of the table "Dataset"

| Caption           | Type   | Description        |
|:----------------|:-------------|:-------------|
| Row Part ID | ![](./img/string.svg) Integer | Number of the original string's part   |
| Row Part   | ![](./img/string.svg) String | Contains parts of the original string |
