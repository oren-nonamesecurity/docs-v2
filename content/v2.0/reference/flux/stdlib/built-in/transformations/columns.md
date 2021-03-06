---
title: columns() function
description: >
  The `columns()` function lists the column labels of input tables.
  For each input table, it outputs a table with the same group key columns,
  plus a new column containing the labels of the input table's columns.  
aliases:
  - /v2.0/reference/flux/functions/transformations/columns
  - /v2.0/reference/flux/functions/built-in/transformations/columns/
menu:
  v2_0_ref:
    name: columns
    parent: built-in-transformations
weight: 401
---

The `columns()` function lists the column labels of input tables.
For each input table, it outputs a table with the same group key columns,
plus a new column containing the labels of the input table's columns.
Each row in an output table contains the group key value and the label of one column of the input table.
Each output table has the same number of rows as the number of columns of the input table.

_**Function type:** Transformation_

```js
columns(column: "_value")
```

## Parameters

### column
The name of the output column in which to store the column labels.
Defaults to `"_value"`.

_**Data type:** String_

## Examples
```js
from(bucket: "example-bucket")
  |> range(start: -30m)
  |> columns(column: "labels")
```

##### Get every possible column label in a single table
```js
from(bucket: "example-bucket")
  |> range(start: -30m)
  |> columns()
  |> keep(columns: ["_value"])
  |> group()
  |> distinct()
```

<hr style="margin-top:4rem"/>

##### Related InfluxQL functions and statements:
[SHOW MEASUREMENTS](https://docs.influxdata.com/influxdb/latest/query_language/schema_exploration/#show-measurements)  
[SHOW FIELD KEYS](https://docs.influxdata.com/influxdb/latest/query_language/schema_exploration/#show-field-keys)  
[SHOW TAG KEYS](https://docs.influxdata.com/influxdb/latest/query_language/schema_exploration/#show-tag-keys)  
[SHOW SERIES](https://docs.influxdata.com/influxdb/latest/query_language/schema_exploration/#show-tag-keys)
