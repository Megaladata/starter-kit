# Calendar generator

[Back to the list of components](../README.md)

## Purpose

The component allows you to generate a time series between specified dates. The interval between dates is specified by the variable **Period type**. Possible values:

* **d** — day;
* **w** — week (in accordance with the international standard [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601));
* **m** — month;
* **q** — quarter;
* **y** — year.

## Input Ports

| Name       | Type      |
|:-----------|:----------|
| Dates      | Variables |

### Variables it "Dates" Port

| № | Caption           | Type       | Value                                         |
|--:|:------------------|:-----------|:----------------------------------------------|
| 1 | Initial period    | ![](./img/datetime.svg) Date/Time | 01.01.2023, 12:00 AM   |
| 2 | Final period      | ![](./img/datetime.svg) Date/Time | 12.31.2023, 12:00 AM   |
| 3 | Period type       | ![](./img/string.svg) String      | d                      |

## Output Ports

| Name                | Type       |
|:--------------------|:-----------|
| Data set            | Table      |

### Structure of the "Dataset" Table

| Caption      | Type                               | Description                  |
|:-------------|:-----------------------------------|:-----------------------------|
| Calendar     | ![](./img/datetime.svg) Date/Time  | Generated time series        |
