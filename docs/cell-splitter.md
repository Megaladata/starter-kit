# Row splitter

[Back to the list of components](../README.md)

## Purpose

Enables the division of a string value with delimiters into multiple fields. Only one delimiter (set in the variable) is taken into account. The output produces a dynamic number of fields, depending on the maximum number of parts in the input strings.

## Input Ports

| Name             | Type        |
|:---------------------|:-----------|
| Input data set	 | Table    |
| Variables	        | Variables |

### Structure of the table "Input Dataset"

| Caption          | Type   | Description       |
|:---------------|:--------------------------------|:-----------------------------------------------------------------------|
| Input String | ![](./img/string.svg) String | Strings with delimiters, the values of which need to be split into separate fields |

### Variables in the "Variables" port

| Caption       | Тип                             | Value    |
|:------------|:--------------------------------|:------------|
| Delimiter | ![](./img/string.svg) String | ,           |

**Delimiter** - Specifies the delimiter present in the input string. Based on this, parts of the string and their number are determined.

## Output ports

| Caption              | Type        |
|:----------------------|:-----------|
| Data set         | Table    |

### Structure of the table "Dataset"

| Caption          | Type        | Description        |
|:---------------|:-------------|:-------------------------|
| Input String | ![](./img/string.svg) String | Original string |
| n              | ![](./img/string.svg) String | The remaining fields contain parts of the original string, where n is the part number, starting from 1 (recorded in the field label) |
