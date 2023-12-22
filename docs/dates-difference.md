# Date difference

[Back to the list of components](../README.md)

## Purpose

The component allows you to calculate the difference between two dates. It can take either a dataset with two columns or two variables as input.

## Output Ports

| Name                  | Type       |
|:----------------------|:-----------|
| Dates             | Table      |
| Dates             | Variables  |

### Structure of the "Dates" Table

| Caption            | Type    | Description          |
|:-----------------|:-------------|:---------------------|
| Date Difference  | ![](./img/datetime.svg) Date/Time  | Calculated difference between two dates|

### Variables in the "Variables" Port

| № | Caption           | Type     | Description  |
|--:|:----------------|:----------------------------------|:-----------------------------|
| 1 | Date 1          | ![](./img/datetime.svg) Date/Time | The first input date         |
| 2 | Date 2          | ![](./img/datetime.svg) Date/Time | The second input date        |

### Structure of the "DataSet" Table

| Caption                    | Type                              | Description                               |
|:-------------------------|:----------------------------------|:------------------------------------------|
| Difference               | ![](./img/realnumber.svg) Float   | Mathematical difference between dates    |
| Days (Total)             | ![](./img/integer.svg) Integer    | Difference in total days                  |
| Hours (Total)            | ![](./img/integer.svg) Integer    | Difference in total hours                 |
| Minutes (Total)          | ![](./img/integer.svg) Integer    | Difference in total minutes               |
| Seconds (Total)          | ![](./img/integer.svg) Integer    | Difference in total seconds               |
| Hours (Remainder)        | ![](./img/integer.svg) Integer    | Number of hours considering full days    |
| Minutes (Remainder)      | ![](./img/integer.svg) Integer    | Number of minutes considering hours      |
| Seconds (Remainder)      | ![](./img/integer.svg) Integer    | Number of seconds considering minutes    |
| Days difference        | ![](./img/string.svg) String      | Time elapsed between dates in days        |
| Hours difference       | ![](./img/string.svg) String      | Time elapsed between dates in hours       |
| Date 1                   | ![](./img/datetime.svg) Date/Time | Original time series 1                    |
| Date 2                   | ![](./img/datetime.svg) Date/Time | Original time series 2                    |

### Variables in the "Variables" Port

| №  | Caption                 | Type                              | Value               |
|---:|:----------------------|:----------------------------------|:--------------------|
| 1  | Difference            | ![](./img/realnumber.svg) Float   | 1.91                |
| 2  | Days (Total)          | ![](./img/integer.svg) Integer    | 1                   |
| 3  | Hours (Total)         | ![](./img/integer.svg) Integer    | 45                  |
| 4  | Minutes (Total)       | ![](./img/integer.svg) Integer    | 2754                |
| 5  | Seconds (Total)       | ![](./img/integer.svg) Integer    | 165264              |
| 6  | Hours (Remainder)     | ![](./img/integer.svg) Integer    | 21                  |
| 7  | Minutes (Remainder)   | ![](./img/integer.svg) Integer    | 54                  |
| 8  | Seconds (Remainder)   | ![](./img/integer.svg) Integer    | 24                  |
| 9  | Days difference    | ![](./img/string.svg) String      | 21:54:24            |
| 10 | Hours difference    | ![](./img/string.svg) String      | 45:54:24            |
| 11 | Date 1                | ![](./img/datetime.svg) Date/Time | 01.01.2023 12:30:48 |
| 12 | Date 2                | ![](./img/datetime.svg) Date/Time | 03.01.2023 10:25:12 |

