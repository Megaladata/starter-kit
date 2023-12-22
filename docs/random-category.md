# Random category JS

[Back to the list of components](../README.md)

## Purpose

Assigns n-random categories to each object from the list, considering the probability of category selection (or without considering probability). Categories are not repeated for a single object. The component utilizes JavaScript code.

## Input Ports

| Name          | Type       |
|:--------------|:-----------|
| Objects       | Table      |
| Categories    | Table      |
| Values        | Table      |
| Variables     | Variables  |

### Structure of the "Objects" Table

| Caption      | Type      | Description     |
|:-----------|:------------------------------|:--------------------------------------------|
| Object     | ![](./img/string.svg) String  | Identifier or name of the object (e.g., customer) |

### Structure of the "Categories" Table

| Caption         | Type         | Description      |
|:--------------|:------------|:--------------------|
| Category      | ![](./img/string.svg) String      | Identifier or name of the category (e.g., product) |

### Structure of the "Values" Table

| Caption         | Type        | Description       |
|:--------------|:------|:----------|
| Value         | ![](./img/realnumber.svg) Float   | Value related to the category (e.g., purchase count) |

This port is optional.

### Variables in the "Variables" Port

| #  | Caption                       | Type                          | Value |
|---:|:----------------------------|:------------------------------|:------|
| 1  | Number of Categories        | ![](./img/integer.svg) Integer| 3     |

## Output Ports

| Name          | Type       |
|:--------------|:-----------|
| Dataset       | Table      |

### Structure of the "Dataset" Table

| Caption         | Type       | Description        |
|:--------------|:------|:--------|
| Object        | ![](./img/string.svg) String        | Identifier or name of the object       |
| Category      | ![](./img/string.svg) String        | Category assigned to the object        |

## Algorithms

1. Calculation of category selection probability: Indicator per category / Total sum of indicators across all categories.
2. Establishment of category boundaries. Upper boundary is the cumulative probability value.
3. Generation of a random number for each object and checking which category boundaries it falls into.
4. Checking whether the category has already been assigned to the object. If yes, repeat steps 3 and 4.
