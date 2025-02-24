# Column filter JS (Regex)

[Back to the list of components](../README.md)

## Purpose

Designed for selecting columns from the input dataset based on a regular expression.

The component uses JavaScript code (JavaScript component).

## Input Ports

| Name            | Type       |
|:----------------|:-----------|
| Dataset         | Table      |
| Variables         | Variables      |


### Structure of the "Dataset" Table

The structure of the table is not defined, auto-synchronization is enabled in the port.

### Variables in the "Variables" Port

| № | Caption     | Type            |
|:--|:-------------------------|:-------|
| 1 | Filter condition ([JS regular expression](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_expressions))     |![](./img/string.svg) String         |
| 2 | Name of the property to which the filter is applied (default: Name)      | ![](./img/string.svg) String    |

**Filter condition (JS regular expression)** — regular expression by which fields will be selected it the resulting table.

**Name of the property to which the filter is applied (default: Name)** — filtering attribute. Value can be:

| Value                 |
|:----------------------|
| Name                  |
| DisplayName (Caption) |
| DataType              |
| DataKind              |
| UsageType             |

The following numeric designations must be used for filtering by column property.

Data Type:

| Type           | Value      |
|:---------------|:-----------|
| None           | 0          |
| Boolean        | 1          |
| DateTime       | 2          |
| Float          | 3          |
| Integer        | 4          |
| String         | 5          |
| Variant        | 6          |

Data Kind:

| Kind           | Value      |
|:---------------|:-----------|
| Undefined      | 0          |
| Continuous     | 1          |
| Discrete       | 2          |

Usage Type:

| Type           | Value      |
|:---------------|:-----------|
| Unspecified    | 0          |
| Excluded       | 1          |
| Useless        | 2          |
| Used           | 3          |
| Input          | 3          |
| Active         | 3          |
| Output         | 4          |
| Predicted      | 4          |
| Key            | 5          |
| Group          | 6          |
| Value          | 7          |
| Transaction    | 8          |
| Item           | 9          |


## Output Ports

| Name            | Type       |
|:----------------|:-----------|
| Dataset         | Table      |

### Structure of the "Dataset" Table

The structure of the table will correspond to the list of columns selected by matching the regular expression fed to the input port  **Filter condition (JS regular expression)**.
