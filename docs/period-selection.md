# Period selection

[Back to the list of components](../README.md)

## Purpose

It allows converting values in a **Date/Time** field into a period. The period can be represented by its first or last date, and it's possible to segment periods according to ISO (month, week).

Typically, the component is used with the aim of subsequent grouping by period with various options.

## Input Ports

| Name             | Type        |
|:---------------------|:-----------|
| Input data set	 | Table    |
| Variables	        | Variables |

### Structure of the "Input dataset" table

| Caption        | Type                                | Description                                                |
|:-------------|:-----------------------------------|:--------------------------------------------------------|
| Object ID	   | ![](./img/string.svg) String    | Identifier of the object: client, product, event, etc  |
| Date         | ![](./img/datetime.svg)  Date/Time | Date that needs to be transformed  |

### Variables in the "Variables" port

| № | Caption           | Type                               | Value  |
|:--|:----------------|:----------------------------------|:----------|
| 1 | Period Type    | ![](./img/string.svg) String   | m         | 
| 2 | First Day	    | ![](./img/logical.svg) Logical | true      |

1. Allowed period types:

* y — year;
* q — quarter;
* m — month (default);
* im — ISO month;
* w — week;
* iw — ISO week;
* d — day.

2. **First Day** — if set to **true** (default), the period in the output table will be represented by its first date; otherwise, it will be represented by its last date.

## Output Ports

| Название   | Тип     |
|:-----------|:--------|
| Dataset | Table |

### Structure of the "Dataset" table

| Caption      | Type                                | Description                                                |
|:-----------|:-----------------------------------|:--------------------------------------------------------|
| Object ID	 | ![](./img/string.svg) String    | Object Identifier       |
| Date       | ![](./img/datetime.svg)  Date/Time	 | Original Date |
| Period     | ![](./img/datetime.svg)  Date/Time	 | Period to which the original date refers  |
