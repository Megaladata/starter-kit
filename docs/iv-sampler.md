# IV selection

[Back to the list of components](../README.md)

## Purpose  

The component is designed for post-processing the results of the **Coarse Classes** component:

* Selecting columns that contain the coarse class label (by default, such columns have a postfix _ClassMark);
* Selecting significant columns (the list of significant columns is provided separately and can be taken from the output of the coarse classes).

## Input Ports

| Name                    | Type         |
|:------------------------|:-------------|
| Input Dataset           | Table        |
| Column Significances    | Table        |
| Variables               | Variables    |

### Structure of the "Input Dataset" Table

The input should be the output dataset from the first output port of the **Coarse Classes** component.

### Structure of the "Column Significances" Table

| Caption             | Type                             | Description |
|:------------------|:---------------------------------|:------------|
| Column Name       | ![](./img/string.svg) String     |             |
| Column Display Name      | ![](./img/string.svg) String     |             |
| Significance | ![](./img/string.svg) String    |             |

This dataset can be taken from the third output port of the **Coarse Classes** component after filtering the required columns by significance.

### Variables in the "Variables" Port

| Caption               | Type                             | Value       |
|:--------------------|:---------------------------------|:------------|
| Excluded Columns    | ![](./img/string.svg) String     | Id,Event    |
| Label Postfix       | ![](./img/string.svg) String     | _ClassMark  |

Changing the **Label Postfix** variable is not recommended if you are using the results of the **Coarse Classes** component. The excluded columns variable should contain a comma-separated list of field names that need to be included "as is" in the component's output (usually, this is the identifier field and the event field).

## Output Ports

| Name                    | Type     |
|:------------------------|:---------|
| Output Dataset          | Table    |

### Structure of the "Output Dataset" Table

The structure of the table corresponds to the transformed input dataset.
