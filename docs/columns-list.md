# Fields list JS

[Back to the list of components](../README.md)

## Purpose

The component allows you to obtain information about input fields: name, caption, type, and field kind.

## Input Ports

| Name                     | Type       |
|:-------------------------|:-----------|
| Input Data Source        | Table      |
| Input Variables        | Variables      |

### Structure of the "Input Data Source" Table

The structure of the table is not defined, auto-synchronization is enabled on the port.

### Variables in the "Input Variables" Port

The structure of the variables is not defined, auto-synchronization is enabled on the port.

## Output Ports

| Name                    | Type       |
|:------------------------|:-----------|
| Output Data Source      | Table      |

### Structure of the "Output Data Source" Table

| Caption           | Type                                | Description                                                             |
|:----------------|:-----------------------------------|:------------------------------------------------------------------------|
| Field.Name      | ![](./img/string.svg) String        | Displays the field name                                                 |
| Field.Caption     | ![](./img/string.svg) String        | Displays the field label                                                |
| Field.Type      | ![](./img/string.svg) String        | Displays the field type: Integer, Logical, Date/Time, Float, String, Continuous |
| Field.Kind      | ![](./img/string.svg) String        | Displays the field kind: Undefined, Continuous, Discrete                |

