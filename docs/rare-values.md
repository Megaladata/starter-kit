# Rare values

[Back to the list of components](../README.md)

## Purpose

Search for rare field values, formation of a replacement table taking into account the threshold frequency for rare values and the condition for replacing single values.
## Input Ports

| Name             | Type        |
|:---------------------|:-----------|
| Input data set	 | Table    |
| Variables	        | Variables |

### Structure of the "Input dataset" table

| Caption         | Type                                 | Description                                            |
|:--------------|:------------------------------------|:----------------------------------------------------|
| ID | ![](./img/undefined.svg) Variant | Object identifier        |
| Key          | ![](./img/string.svg) String     | Field name the value belongs to |
| Value      | ![](./img/undefined.svg) Variant | Field value|

### Variables in the "Variables" Port

| № | Caption                     | Type                                    | Value   |
|:--|:--------------------------|:---------------------------------------|:-----------|
| 1 | Bound	       | ![](./img/realnumber.svg) FLoat | 0,0125     |
| 2 | Replace Flag	 | ![](./img/logical.svg) Logical      | false      |
| 3 | Replace	         | ![](./img/string.svg) String        | Other     |

1. **Bound** — a threshold frequency of occurrence value; anything below is considered rare. User-defined.

2. **Replace Flag** — determines whether to replace the field value if only one rare value is found in it (true), or to keep the list of unique values in the field (false, by default).

3. **Replace** — the value to replace the rare values with. User-defined.

## Output Ports

| Name              | Type        |
|:----------------------|:-----------|
| Dataset         | Table    |
| Replaced Values   | Table    |
| Replacement Table        | Table    |

### Structure of the "Dataset" Table

| Caption             | Type                                   | Description                                                                                |
|:------------------|:--------------------------------------|:----------------------------------------------------------------------------------------|
| Identifier     | ![](./img/string.svg) String   | Identifier of the object                     |
| Key              | ![](./img/string.svg) String       | Field name related to the value              |
| Value | ![](./img/string.svg) String    | The value that was input      |
| New Value   | ![](./img/string.svg) String     | If the original value is considered rare, the value from the **Replace** variable is shown |
| Flag Replaced          | ![](./img/logical.svg) Logical |Flag indicating whether a replacement was made |


### Structure of the "Replaced Values" Table

| Caption       | Type    | Description           |
|:------------------|:--------------|:----------|
| Key              | ![](./img/string.svg) String     | Field whose value was replaced  |
| Value | ![](./img/undefined.svg) ![](./img/string.svg) String | Value that was replaced.        |
| Replace Quantity  | ![](./img/integer.svg) Integer        | Number of times the value was replaced in the input dataset |

### Structure of the "Replacement Table"

| Caption   | Type     | Description     |
|:------------------|:----------|:---------------------------|
| Key              | ![](./img/string.svg) String     | Field whose value was replaced   |
| Value | ![](./img/string.svg) String | Value that was replaced       |
| New value    | ![](./img/string.svg) String | Value it was replaced with |

## Algorithms

For each unique value in a specific field, the share of objects is calculated. All object values, the share of which is below the threshold, are replaced with a string value specified in the **Replace with** variable (by default **Other**).
