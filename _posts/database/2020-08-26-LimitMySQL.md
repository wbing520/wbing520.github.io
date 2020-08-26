---
layout: post
title: MySQL - Limit
categories: Database
description: how to use limit in MySQL
keywords: Database, Limit
---

## MySQL LIMIT

LIMIT is used to constrain the SELECT statement for the number of rows returned.

```sql
#return 30 recoreds.
SELECT * FROM Orders LIMIT 30;

#return records [16 - 25], using OFFSET
# return only 10 records, start on record 16 (OFFSET 15)
SELECT * FROM Orders LIMIT 10 OFFSET 15;

# A shorter version using a comma
SELECT * FROM Orders LIMIT 15, 10;
```
