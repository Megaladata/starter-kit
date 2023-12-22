# Category to number

[Back to the list of components](../README.md)

## Purpose

This component encodes each category into an integer. The distance between consecutive integers depends on the variable **Increment**.

## Input Ports

| Name         | Type       |
|:-------------|:-----------|
| Categories   | Table      |
| Variables    | Variables  |

### Structure of the "Nominal Data" Table

| Caption      | Type                            | Description                               |
|:-----------|:-------------------------------|:------------------------------------------|
| Category   | ![](./img/string.svg) String   | Name or identifier of the category        |

### Variables in the "Variables" Port

| #  | Caption              | Type                              | Value   |
|---:|:-------------------|:----------------------------------|:--------|
| 1  | Start Value      | ![](./img/integer.svg) Integer    | 0       |
| 2  | Increment          | ![](./img/integer.svg) Integer    | 1       |
| 3  | Count Empty       | ![](./img/logical.svg) Logical    | true    |

1. **Start Value** — the value assigned to the first category.

2. **Increment** — categories are assigned numbers according to the formula: *Initial Value + Increment &#42; Category Position*.

3. **Count Empty** — specifies how to handle empty values. When set to **true** (default), an empty category will be assigned a number. When set to **false**, empty categories will remain empty.

## Output Ports

| Name           | Type       |
|:---------------|:-----------|
| DataSet       | Table      |
| Replacement Table | Table   |

### Structure of the "Data Set" Table

| Caption             | Type                         | Description                  |
|:------------------|:----------------------------|:-----------------------------|
| Category (Replaced)| ![](./img/integer.svg) Integer| Numeric values of categories|

### Structure of the "Replacement Table" Table

| Caption                | Type                              | Description                                       |
|:---------------------|:----------------------------------|:---------------------------------------------------|
| Category   | ![](./img/string.svg) String      | List of unique category values                     |
| Category (Replaced)   | ![](./img/integer.svg) Integer    | List of unique numbers assigned to categories     |
