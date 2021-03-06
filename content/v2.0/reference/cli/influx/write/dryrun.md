---
title: influx write dryrun
description: >
  The 'influx write dryrun' command prints write output to stdout instead of writing
  to InfluxDB. Use this command to test writing data.
menu:
  v2_0_ref:
    name: influx write dryrun
    parent: influx write
weight: 101
v2.0/tags: [write]
---

The `influx write dryrun` command prints write output to stdout instead of writing
to InfluxDB. Use this command to test writing data.

Supports [line protocol](/v2.0/reference/syntax/line-protocol) and
[annotated CSV](/v2.0/reference/syntax/annotated-csv).
Output is always **line protocol**.

## Usage
```
influx write dryrun [flags]
```

## Flags
| Flag                | Description                                 | Input type | {{< cli/mapped >}}   |
|:----                |:-----------                                 |:----------:|:------------------   |
| `-b`, `--bucket`    | Bucket name                                 | string     | `INFLUX_BUCKET_NAME` |
| `--bucket-id`       | Bucket ID                                   | string     | `INFLUX_BUCKET_ID`   |
| `-f`, `--file`      | File to import                              | string     |                      |
| `--format`          | Input format (`lp` or `csv`, defaults `lp`) | string     |                      |
| `-h`, `--help`      | Help for the `dryrun` command               |            |                      |
| `-o`, `--org`       | Organization name                           | string     | `INFLUX_ORG`         |
| `--org-id`          | Organization ID                             | string     | `INFLUX_ORG_ID`      |
| `-p`, `--precision` | Precision of the timestamps (default `ns`)  | string     | `INFLUX_PRECISION`   |

{{% cli/influx-global-flags %}}
