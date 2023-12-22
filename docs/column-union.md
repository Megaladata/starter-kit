# Joining JS Columns

[Back to the list of components](../README.md)

## Purpose

Component for combining columns into one row using an arbitrary separator.

## Input Ports

| Name              | Type      |
|:------------------|:--------- |
| Dataset  | Table     |
| Input Variables | Variables |

### Structure of "Dataset"

The table structure is not defined, auto-synchronization is enabled on the port.

### Variables in "Input Variables" Port

| № | Caption          | Type       | Value       |
|:--|:---------------|:--------------|:------------|
| 1 | Separator      | ![](./img/string.svg) String         | ,           |

## Output Ports

| Name                   | Type       |
|:-----------------------|:-----------|
| Output Dataset         | Table      |

### Structure of the "Output Dataset" Table

| Caption              | Type         | Description             |
|:-------------------|:-----|:------------------------|
| Output String      | ![](./img/string.svg) String      | String after merging    |
