# Event labeling

[Back to the list of components](../README.md)

## Purpose

Event labeling for a list of objects within a transaction time window.
This is useful, for instance, when one needs to label a binary field with customer visits to a store over a month.

For input objects and a time window set by dates, an **Event** field is formed. It is `0` (`FALSE`) if no transaction was found for the given object within the transactions, and `1` (`TRUE`) if at least one transaction was encountered. The time window is set by two dates, **Start Date** and **End Date**, and inclusion within the window is checked by the condition >= **Start Date** and < **End Date**.

## Input Ports

| Name            | Type        |
|:--------------------|:-----------|
| List of Objects     | Table    |
| Transactions          | Table    |
| Variables          | Variables |

### Structure of the "List of Objects" table

| Caption         | Type        | Description    |
|:----------------|:------------------------|:------|
| Object ID   | ![](./img/string.svg) String  | Unique identifier of the object|

### Structure of the "Transactions" table

| Caption           | Type     | Description         |
|:----------------|:----------|:------------|
| Object ID       | ![](./img/string.svg) String        | Unique object identifier |
| Trade Date | ![](./img/datetime.svg) Date/Time    | Date and time of the transaction |


### Variables in the "Variables" port

| № | Caption           | Type       | Value   |
|:--|:----------------|:----------------------|:-----------|
| 1 | Start Date	     | ![](./img/datetime.svg) Date/Time  | null       |
| 2 | End Date	  | ![](./img/datetime.svg) Date/Time  | null       |


1. **Start Date** — The initial date from which the event observation begins (including this date).
2. **End Date** — The final date on which the event observation ends (excluding this date).

If the dates are not set (by default), then the event observation is conducted across all transactions.

## Output ports

| Name         | Type        |
|:-----------------|:-----------|
| Events          | Table    |

### Structure of the "Events" table

| Caption           | Type    | Description      |
|:----------------|:----------|:---------------|
| Object ID | ![](./img/string.svg) String     | Unique identifier of the object |
| Event         | ![](./img/integer.svg) Integer  | Event 0/1  |
| Event_L         | ![](./img/logical.svg) Logical   | Event TRUE/FALSE|

