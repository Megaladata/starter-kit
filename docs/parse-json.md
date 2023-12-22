# JSON Parser JS

[Back to the list of components](../README.md)

## Purpose

A simple component for parsing JSON strings and extracting data from them.

## Input Ports

| Name                      | Type       |
|:--------------------------|:-----------|
| Input Data Source         | Table      |
| Input Variables           | Variables  |

### Structure of the "Input Data Source" Table

| Caption          | Type        | Description         |
|:---------------|:----------------------|:--------------------|
| JSON String    | ![](./img/string.svg) String       | JSON formatted string|

### Variables in the "Input Variables" port

| № | Caption        | Type                            | Value   |
|:--|:-------------|:--------------------------------|:--------|
| 1 | JSON String | ![](./img/string.svg) String    | null    |

## Output Ports

| Name                    | Type       |
|:------------------------|:-----------|
| Output Dataset          | Table      |

## Structure of the "Output Dataset" Table

| Caption          | Type                                | Description                            |
|:---------------|:-----------------------------------|:---------------------------------------|
| Response Index | ![](./img/string.svg) String       | Identifier of the input dataset row     |
| parent         | ![](./img/string.svg) String       | parent of the JSON element              |
| key            | ![](./img/string.svg) String       | identifier of the JSON element          |
| type           | ![](./img/string.svg) String       | type of the JSON element                |
| value          | ![](./img/infinity.svg) Variable   | value of the JSON element               |
