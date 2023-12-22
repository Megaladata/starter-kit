# Objects sampling

[Back to the list of components](../README.md)

## Purpose

Selects a subset of objects of a specified size from a set of transactions.

## Input Ports

| Name            | Type        |
|:--------------------|:-----------|
| Events of objects    | Table    |
| Variables          | Variables |

### Object Events Table Structure

| Caption      | Type      | Description     |
|:-----------|:--------|:-------|
| Object     | ![](./img/string.svg) String    | Object ID or name|

### Variables in the "Variables" port

| № | Caption    | Type        | Value |
|:--|:------|:--------|:---------|
| 1 | Size %         | ![](./img/realnumber.svg) Float  | 10,00    |

**Percentage Size** — the percentage of objects to be outputted.

## Output Ports

| Name            | Type        |
|:--------------------|:-----------|
| Object sampling    | Table    |

### Structure of the "Object Events" table

| Caption     | Type               | Description       |
|:----------|:-----------------------------------|:-----------------------------------------------------|
| Object    | ![](./img/string.svg) String    | A list of objects (specified percentage of all objects)  |
