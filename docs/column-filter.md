# Column filter JS

[Back to the list of components](../README.md)

## Purpose

Designed for selecting columns from the input dataset based on a list. Operates in two modes:

* Keeps columns in the output dataset whose names are in the list.
* Excludes columns from the output dataset whose names are in the list.

The component uses JavaScript code (JavaScript component).

## Input Ports

| Name            | Type       |
|:----------------|:-----------|
| Dataset         | Table      |
| List of columns     | Table      |
| Variables       | Variables  |

### Structure of the "Dataset" Table

The structure of the table is not defined, auto-synchronization is enabled in the port.

### Structure of the "List of columns" Table

| Caption           | Type    | Description   |
|:----------------|:----|:----------------------------|
| Column Names    | ![](./img/string.svg) String        | List of column names from the input dataset to be kept/excluded in the output      |

This port is optional.

### Variables in the "Variables" Port

| № | Caption     | Type            | Value      |
|:--|:-------------------------|:-------|:-----------|
| 1 | Exclude Fields by List   | ![](./img/logical.svg) Logical      | true       |
| 2 | List of fields               | ![](./img/string.svg) String        | null       |

**Exclude Fields by List**:

* **true** — columns listed in the input **Column List** or specified in the **List of field** variable will be excluded from the output dataset, default mode;
* **false** — only columns listed in the input **Column List** or specified in the **List of fields** variable will be included in the output dataset.

**List of fields** — column names to be kept/excluded from the output dataset, listed separated by commas. This list takes priority over the **Column List** table when filled.

## Output Ports

| Name            | Type       |
|:----------------|:-----------|
| Dataset         | Table      |

### Structure of the "Dataset" Table

The structure of the table will correspond to the list of columns on the input port **Column List**.
