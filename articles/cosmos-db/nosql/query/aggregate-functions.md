---
title: Aggregate functions in Azure Cosmos DB
description: Learn about SQL aggregate function syntax, types of aggregate functions supported by Azure Cosmos DB.
author: seesharprun
ms.service: cosmos-db
ms.subservice: nosql
ms.custom: ignite-2022
ms.topic: conceptual
ms.date: 12/02/2020
ms.author: sidandrews
ms.reviewer: jucocchi
---
# Aggregate functions in Azure Cosmos DB
[!INCLUDE[NoSQL](../../includes/appliesto-nosql.md)]

Aggregate functions perform a calculation on a set of values in the `SELECT` clause and return a single value. For example, the following query returns the count of items within a container:

```sql
    SELECT COUNT(1)
    FROM c
```

## Types of aggregate functions

The API for NoSQL supports the following aggregate functions. `SUM` and `AVG` operate on numeric values, and `COUNT`, `MIN`, and `MAX` work on numbers, strings, Booleans, and nulls.

| Function | Description |
|-------|-------------|
| [AVG](aggregate-avg.md) | Returns the average of the values in the expression. |
| [COUNT](aggregate-count.md) | Returns the number of items in the expression. |
| [MAX](aggregate-max.md) | Returns the maximum value in the expression. |
| [MIN](aggregate-min.md) | Returns the minimum value in the expression. |
| [SUM](aggregate-sum.md) | Returns the sum of all the values in the expression. |


You can also return only the scalar value of the aggregate by using the VALUE keyword. For example, the following query returns the count of values as a single number:

```sql
    SELECT VALUE COUNT(1)
    FROM Families f
```

The results are:

```json
    [ 2 ]
```

You can also combine aggregations with filters. For example, the following query returns the count of items with the address state of `WA`.

```sql
    SELECT VALUE COUNT(1)
    FROM Families f
    WHERE f.address.state = "WA"
```

The results are:

```json
    [ 1 ]
```

## Remarks

These aggregate system functions will benefit from a [range index](../../index-policy.md#includeexclude-strategy). If you expect to do an `AVG`, `COUNT`, `MAX`, `MIN`, or `SUM` on a property, you should [include the relevant path in the indexing policy](../../index-policy.md#includeexclude-strategy).

## Next steps

- [Introduction to Azure Cosmos DB](../../introduction.md)
- [System functions](system-functions.md)
- [User defined functions](udfs.md)
