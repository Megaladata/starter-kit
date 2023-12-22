# Fragmentation

[Back to the list of components](../README.md)

## Purpose

The component is designed to divide a dataset into batches of a specified size. It is used when there is a need to execute a scenario or a segment of a scenario in parts.

A simple division is applied - counting the number of rows for each identifier and summing them up until the batch size specified in the variable is reached.

## Input Ports

| Name             | Type        |
|:---------------------|:-----------|
| Object ID	 | Table    |
| Variables	        | Variables |

### Structure of the table "Object Identifier"

| Caption  | Type | Description |
|:-----------------------|:-------|:----------|
| Object ID  | ![](./img/string.svg) String | Field by which the division is being carried out |

**Please note**: for the **Object ID** field, you need to input the actual number of records where each identifier is present (NOT a list of unique values) since the segmentation will be based on calculating the number of records for each object.

### Variables in the "Variables" port

| № | Caption                | Type                          | Description |
|:--|:---------------------|:-----------------------------|:---------|
| 1 | Number of rows per batch	| ![](./img/integer.svg) Integer | 100      |

**Number of rows per batch** - the maximum allowable size of a batch, set by the user.

## Output ports

| Caption              | Type        |
|:----------------------|:-----------|
| Data set         | Table    |
| Batch boundaries | Table    |

### Structure of the "Dataset" table

| Caption  | Type   | Description         |
|:------------|:------------------|:-------------------|
| Object ID            | ![](./img/string.svg) String  | Unique object identifier           |
| Batch number	                      | ![](./img/integer.svg) Integer     | The batch number the object belongs to  |

### Structure of the "Batch boundaries" table

| Caption         | Type   | Description   |
|:----------------|:-------------------|:-------------------------|
| Batch Number                                     | ![](./img/integer.svg) Batch Number     |     Unique batch number        |
| ObjectID First                   | ![](./img/string.svg) String  | ID of the first object in the batch (sorted in ascending order by the string field)    |
| ObjectID Last | ![](./img/string.svg) String  | ID of the last object in the batch (sorted in ascending order by the string field) |
