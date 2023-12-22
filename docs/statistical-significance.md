# Statistical significance

[Back to the list of components](../README.md)

## Purpose

Component for Testing Statistical Significance.

This component is used for testing statistical significance using a one-sided T-test, two-sided T-test, or Mann-Whitney U-test.

### Input Ports

| Name                 | Type       |
|:---------------------|:---------- |
| Percentage by groups   | Table      |
| Variables            | Variables  |

### Structure of "Group Percentages" Table

| Caption                 | Type                                | Description                                                                                          |
|:----------------------|:------------------------------------|:-----------------------------------------------------------------------------------------------------|
| Control Value %       | ![](./img/Floatnumber.svg) Float      | The percentage of events in the control group (the group that did not receive treatment or intervention) |
| Test Value %          | ![](./img/Floatnumber.svg) Float      | The percentage of events in the test group (the group that received treatment or intervention)         |

### Variables in "Variables" Port

| # | Caption                | Type                                | Value   |
|:--|:---------------------|:------------------------------------|:------- |
| 1 | Significance Level   | ![](./img/realnumber.svg) Float      | 0.05    |
| 2 | Test Type            | ![](./img/integer.svg) Integer      | 0       |

1. **Significance Level** - This is the value used to assess the truth of a result or hypothesis. Popular significance levels include:

   * **0.05** (default);
   * **0.01**;
   * **0.001**.

2. **Test Type** - Can take the following values:

   * **0** (default) - One-sided T-test;
   * **1** - Two-sided T-test;
   * **2** - Mann-Whitney U-test.

### Output Ports

| Name                 | Type       |
|:---------------------|:---------- |
| Variables            | Variables  |

### Variables in the "Variables" Port

| #  | Caption                                 | Type                                     | Description                                                |
|:---|:--------------------------------------|:---------------------------------------- |:----------------------------------------------------------|
| 1  | Statistic Significant             | ![](./img/string.svg) String             | Takes values **Yes** or **No** (see **Additional Literature**)                       |
| 2  | Control Group: Observations Count     | ![](./img/integer.svg) Integer           | Number of observations (records) in the control group in the source data             |
| 3  | Test Group: Observations Count        | ![](./img/integer.svg) Integer           | Number of observations in the test group in the source data                            |
| 4  | Significance Level                    | ![](./img/realnumber.svg) Float            | Chosen significance level                                  |
| 5  | Value                       | ![](./img/realnumber.svg) Float            | Value of T-criterion or U-criterion calculated for groups  |
| 6  | Test Type                             | ![](./img/string.svg) String             | Chosen test                                               |
| 7  | Impact Effect %           | ![](./img/realnumber.svg) Float            | (see **Algorithms**)                                       |
| 8  | Control Group: average                   | ![](./img/realnumber.svg) Float            | Mean value for the control group (Only for T-test)        |
| 9  | Test Group: average                      | ![](./img/realnumber.svg) Float            | Mean value for the test group (Only for T-test)           |
| 10 | Control Group: Variance               | ![](./img/realnumber.svg) Float            | Variance for the control group (Only for T-test)          |
| 11 | Test Group: Variance                  | ![](./img/realnumber.svg) Float            | Variance for the test group (Only for T-test)             |

## Algorithms

1. **Impact of Intervention, %** - If the *Statistically Significant* field is set to **Yes**, then the calculation of the impact of intervention for the T-test will be performed using the formula:

    ![](./img/impact.svg), where:

    * **TestAvg** - the average value for the test sample;
    * **ControlAvg** - the average value for the control sample.

