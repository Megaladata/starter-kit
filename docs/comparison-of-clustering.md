# Clustering comparison

[Back to the list of components](../README.md)

## Purpose

This component is designed to calculate relative quality assessment metrics of two clusterings (similarity measures):

- Rand Index
- Fowlkes-Mallows Index
- Jaccard Index
- Variation of Information.

## Input Ports

| Name              | Type      |
|:------------------|:--------- |
| Input Data Table  | Table     |
| Sample Part | Variables |

### Structure of "Input Data Table"

| Caption            | Type                         | Description                                  |
|:-----------------|:---------------------------- |:-------------------------------------------- |
| ID      | ![](./img/string.svg) String | Identifier of the object                     |
| Cluster Number 1 | ![](./img/integer.svg) Integer| Cluster number of the object in the first clustering |
| Cluster Number 2 | ![](./img/integer.svg) Integer| Cluster number of the object in the second clustering|

### Variables in "Sample Percentage" Port

| # | Caption            | Type                          | Value     |
|:-:|:-----------------|:------------------------------|:----------|
| 1 | Part, % | ![](./img/realnumber.svg) Float | 100       |

**Sample Percentage** - allows you to specify the proportion of objects that will participate in forming pairs for computation. By default, all objects participate (100%).

## Output Ports

| Name     | Type       |
|:---------|:---------- |
| Indexes  | Variables  |

### Variables in "Indexes" Port

| # | Caption                     | Type                          | Description                                                                                   |
|:-:|:--------------------------|:------------------------------|:-----------------------------------------------------------------------------------------------|
| 1 | Rand Index                | ![](./img/realnumber.svg) Float | Value ranges from 0 to 1, where 1 indicates clustering identity                              |
| 2 | Fowlkes-Mallows Index     | ![](./img/realnumber.svg) Float | Often used in hierarchical clustering. 1 indicates clustering identity                       |
| 3 | Jaccard Index             | ![](./img/realnumber.svg) Float | Computed when excluding observations common to both clusterings into different clusters. Higher value indicates closer clustering |
| 4 | Partitioned Difference  | ![](./img/integer.svg) Integer | Number of pairs of objects belonging to different clusters in the clusterings             |

## Additional Resources

1. [Clustering performance evaluation](http://scikit-learn.org/stable/modules/clustering.html#clustering-evaluation)
2. [Fowlkes–Mallows index](https://en.wikipedia.org/wiki/Fowlkes%E2%80%93Mallows_index)
