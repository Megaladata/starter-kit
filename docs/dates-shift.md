# Date Shift

[Back to the list of components](../README.md)

## Purpose

Component for shifting the date by one or multiple units of time measurement.

## Input Ports

| Name       | Type       |
|:-----------|:-----------|
| Dates      | Table      |
| Variables  | Variables  |

### Structure of the "Dates" Table

| Caption         | Type     | Description     |
|:--------------|:-------|:-----------------------|
| Date List     | ![](./img/datetime.svg) Date/Time   | Time series                  |

### Variables in the "Variables" port

| № | Caption             | Type      | Value       |
|--:|:------------------|:-------|:-------------|
| 1 | Shift Direction   | ![](./img/string.svg) String      | +                       |
| 2 | Years             | ![](./img/integer.svg) Integer    | 0                      |
| 3 | Months            | ![](./img/integer.svg) Integer    | 0                      |
| 4 | Days              | ![](./img/integer.svg) Integer    | 0                      |
| 5 | Hours             | ![](./img/integer.svg) Integer    | 0                      |
| 6 | Minutes           | ![](./img/integer.svg) Integer    | 0                      |
| 7 | Seconds           | ![](./img/integer.svg) Integer    | 0                      |

**Shift Direction** — a variable that takes two values:

 * **+** (plus) — adds the specified units of time measurement to the original date (by default);
 * **-** (minus) — subtracts the specified units of time measurement from the original date;

## Output Ports

| Name                    | Type       |
|:------------------------|:-----------|
| Output Dataset          | Table      |

### Structure of the "Output Dataset" Table

| Caption         | Type                                | Description                            |
|:--------------|:------|:--------|
| Date List     | ![](./img/datetime.svg) Date/Time   | Transformed time series                 |
