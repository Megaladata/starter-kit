# List generator

[Back to the list of components](../README.md)

## Purpose

This component allows you to generate a numbered list. The length of the list is determined by the variables **List Start** and **List End**.

## Input Ports

| Name        | Type       |
|:------------|:-----------|
| Variables   | Variables  |

### Variables in the "Variables" Port

| #  | Caption          | Type            | Value |
|---:|:---------------|:----------------|:------|
| 1  | List Start     | ![](./img/integer.svg) Integer | 1     |
| 2  | List End       | ![](./img/integer.svg) Integer | 100   |

If the value of the variable **List Start** is greater than **List End**, an empty dataset is generated.

If the value of the variable **List Start** equals **List End**, a single row is generated.

## Output Ports

| Name                  | Type       |
|:----------------------|:-----------|
| Dataset               | Table      |

### Structure of the "Dataset" Table

| Caption     | Type            | Description         |
|:----------|:----------------|:--------------------|
| List      | ![](./img/integer.svg) Integer | Generated list      |
