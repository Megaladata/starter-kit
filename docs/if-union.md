# IF unify JS

[Back to the list of components](../README.md)

## Purpose

The component takes two datasets as input, one of which is mandatory to be empty. The output retains only the dataset that is not empty. This is used as one of the options for merging branches after the execution of the [Condition Node](https://help.loginom.ru/userguide/processors/control/condition.html).

## Input Ports

| Name                     | Type       |
|:-------------------------|:-----------|
| Input Data Source        | Table      |
| Input Data Source 2      | Table      |

### Structure of the "Input Data Source 1" Table

The structure of the table is not defined, auto-synchronization is enabled on the port.

### Structure of the "Input Data Source 2" Table

The structure of the table is not defined, auto-synchronization is enabled on the port.

## Output Ports

| Name                    | Type       |
|:------------------------|:-----------|
| Output Dataset          | Table      |

### Structure of the "Dataset" Table

The structure of the table corresponds to the structure of the dataset from the port **Input Data Source** or **Input Data Source 2**.
