# Popular objects

[Back to the list of components](../README.md)

## Purpose

Creation of a list of popular items with the grouping of the rest into one category.

## Input Ports

| Name            | Type        |
|:--------------------|:-----------|
| Input Dataset    | Table    |
| Variables          | Variables |

### Structure of the table "Dataset"

| Caption    | Type   | Description    |
|:--------------|:-----------------|:------------------------|
| Object        | ![](./img/string.svg) String        | Object Name    |
| Value   | ![](./img/realnumber.svg) Float | Object value      |

### Variables in the "Variables" port

| № | Caption  | Type          | Description   |
|:--|:---------------|:--------------|:-----------|
| 1 | Popular Object Bound   | ![](./img/integer.svg) Integer        | 10         |
| 2 | Calculate Type         | ![](./img/string.svg) String     | top-k      |
| 3 | Replace                  | ![](./img/string.svg) String     | Other     |

1. **Popular Object Bound** — the number or percentage of objects that will be on the popular list.
2. **Calculation type** — can take values:
   * *top-k* (default) — to highlight a number of popular objects from the total number;
   * *top-%* — to highlight a percentage of popular objects from the total number;
3. **Replace** — the new name to which objects not included in the popular list will be renamed.

## Output ports

| Name              | Type        |
|:----------------------|:-----------|
| Dataset          | Table    |
| Popular objects    | Table    |
| Replaced objects    | Table    |

### Structure of the table "Dataset"

| Caption  | Type       | Description       |
|:---------|:-----------|:--------|
| Source object   | ![](./img/string.svg) String          | Name of the object from the input dataset                         |
| New object     | ![](./img/string.svg) String          | New name of the replaced object|
| Value        | ![](./img/realnumber.svg) Float   | Object's metric     |
| Flag Replaced          | ![](./img/logical.svg) Logical        |**true** — object name was replaced, **false** — no replacement took place|

### Structure of the 'Popular Items' Table

| Caption  | Type   | Description          |
|:--------------------|:-----|:---------------|
| Object              | ![](./img/string.svg) String          | Object name, including those replaced                 |
| Value          | ![](./img/realnumber.svg) Float   | Object's metrics                       |
| Flag Replaced           | ![](./img/logical.svg) Logical        | **true** — object name was replaced, **false** — no replacement took place     |
| Object count | ![](./img/integer.svg) Integer             | Count of replaced and non-replaced objects         |

### Structure of the 'Replaced Items' Table

| Caption         | Type            | Description         |
|:------------------|:---------------------|:-----------|
| Object   | ![](./img/string.svg) String          | Name of the replaced object from the input dataset   |
| New object       | ![](./img/string.svg) String          | New name for the replaced object                       |
| Value        | ![](./img/realnumber.svg) Float   | Object's metric                         |