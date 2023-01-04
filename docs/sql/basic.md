# Basics
[below example is modified from here](https://www.sqltutorial.org/sql-cheat-sheet/)
## Querying
| Purpose | SQL | Description |
|-|-|-|
| Query data in columns c1, c2 from a table | `SELECT c1, c2 FROM t;` ||
| Query all rows and columns from a table | `SELECT * FROM t;` ||
| Query data and filter rows with a condition | `SELECT c1, c2 FROM t WHERE condition` ||
| Query distinct(nonduplicated) rows from a table | `SELECT DISTINCT c1 FROM t WHERE condition` ||
| Sort the result set in ascending or descending order | `SELECT c1, c2 FROM t ORDER BY c1 ASC [DESC];` ||
| Skip offset of rows and return the next n rows | `SELECT * FROM t ORDER BY c1 LIMIT n1 OFFSET n2` | Return only `n1` records, start on record `n2+1` (OFFSET `n2`) |
| Group rows using an `aggregate function` | `SELECT c1, aggregate(c2) FROM t GROUP BY c1` | An aggregate function in SQL performs a calculation on multiple values and returns a single value. e.g. `AVG`, `COUNT`, `MAX`, `MIN`, `SUM`. Note that you can only `SELECT` the column(c1) you `GROUP BY` and the aggregate function with other columns. |
| Filter groups using `HAVING` clause | `SELECT c1, aggregate(c2) FROM t GROUP BY c1 HAVING condition` | You can seen `HAVING` as `GROUP`'s `WHERE` clause  |

## Querying from multiple tables
| Purpose | SQL | Description |
|-|-|-|
| Inner join t1 and t2 | `SELECT c1, c2 FROM t1 INNER JOIN t2 ON condition;` | |
| Left join t1 and t2 | `SELECT c1, c2 FROM t1 LEFT JOIN t2 ON condition;` |
| Right join t1 and t2 | `SELECT c1, c2 FROM t1 RIGHT JOIN t2 ON condition;` | |
| Perform full outer join  | `SELECT c1, c2 FROM t1 FULL OUTER JOIN t2 ON condition;` | |
| Produce a Cartesian product of rows in tables | `SELECT c1, c2 FROM t1 CROSS JOIN t2;` <br> or <br> `SELECT c1, c2 FROM t1, t2;` |
| Another way to perform cross join | `SELECT c1, c2 FROM t1, t2;` | |
| Join t1 to itself using INNER JOIN clause | `SELECT c1, c2 FROM t1 A INNER JOIN t1 B ON condition` |

## Using SQL Operators
| Purpose | SQL | Description |
|-|-|-|
| Combine rows from 2 queries | `SELECT c1, c2 FROM t1 UNION [ALL] SELECT c1, c2 FROM t2;` | The `UNION` operator selects only `distinct` values by default. To allow duplicate values, use `UNION ALL`: |
| Return the intersection of 2 queries | `SELECT c1, c2 FROM t1 INTERSECT SELECT c1, c2 FROM t2;` |
| Subtract(-) a result set from another result set. | `SELECT c1, c2 FROM t1 MINUS SELECT c1, c2 FROM t2;`  |
| Query rows using pattern matching %, _ | `SELECT c1, c2 FROM t1 WHERE c1 [NOT] LIKE pattern` | For example, you can use `LIKE '%a'` to select all customers with a CustomerName starting with "a" |
| Query rows in a list | `SELECT c1, c2 FROM t WHERE c1 [NOT] IN value_list` | `value_list` can come from another subquery. |
| QUERY rows between 2 values | `SELECT c1, c2 FROM t WHERE c1 BETWEEN low and high` | `low` and `high` are number. |
| Check if values in a table is `NULL` or not | `SELECT c1, c2 FROM t WHERE c1 IS [NOT] NULL` |