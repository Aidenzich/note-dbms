## Relational Algebra
| Type | Symbol | Note|
|-|-|-|
| **Union** | $R_1 \cup R_2$ |
| Intersection (交集運算) | $R_1 \cap R_2$ | Intersection defines a relation consisting of a set of all tuple that are in both A and B. |
| Difference (差集運算) | $R_1 - R_2$ |  All rows from the first relation $R_1$ that are not present in the second relation $R_2$. 2 table must being **union compatible**. |
| Cartesian/Cross Product (乘積運算) | $R_1 \times R_2$ | Taking the cross product of two relations essentially taking every combination of the two tables’ tuples. [example](#Cross-Product-Examples)  <br> **SQL:** SELECT * FROM **CUSTOMERS, ORDERS** |
| Select (選擇運算) | $\sigma_{condition}(R)$ | **SQL:WHERE** |
| Project (投影運算) | $\pi_{attributes}(R)$ | **SQL:** SELECT {attributes} FROM ... |
| Join (關聯運算) | $R_1 \Join_{condition} R_2$ | **SQL: Join** |
| Divide (除法運算) | $R_1 \div R_2$ |
| Grouping | $\Im_\text{calculate(attribute)}(R)$ | **SQL: Group by** |

### Relational Join Operation 
A Join operation combines related tuples from different relations, if and only if a given join condition is satisfied. It is denoted by ⋈.
(中: join 操作組合來自不同關係的且滿足給定連接條件的 tuple, 註為⋈)

