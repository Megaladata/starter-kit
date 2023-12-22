# Empty fields generator

[Back to the list of components](../README.md)

## Purpose

In many cases, when an obligatory field is required by a certain component, but it is missing in the analyzed dataset, this component can be used to create four empty fields of different types:

* String;
* Real Number;
* Integer;
* Date/Time.

The created fields can be attached to the dataset using the **Join** node.

## Input Ports

This component has no input ports.

## Output Ports

| Name                  | Type        |
|:----------------------|:------------|
| Dataset               | Table       |

### Structure of the "Dataset" Table

| Caption                 | Type                                    | Description                   |
|:----------------------|:---------------------------------------|:------------------------------|
| Object                | ![](./img/string.svg) String            | Empty string field            |
| Date                  | ![](./img/datetime.svg) Date/Time       | Empty Date/Time field         |
| Real Value            | ![](./img/realnumber.svg) FLoat  | Empty real number field       |
| Integer Value         | ![](./img/integer.svg) Integer         | Empty integer field           |
