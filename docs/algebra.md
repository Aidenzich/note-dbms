## Relational Algebra
| Type | Symbol | Note| SQL Usage |
|-|-|-|-|
| **Union** | $R_1 \cup R_2$ |
| Intersection (交集運算) | $R_1 \cap R_2$ | Intersection defines a relation consisting of a set of all tuple that are in both A and B. |
| Difference (差集運算) | $R_1 - R_2$ |  All rows from the first relation $R_1$ that are not present in the second relation $R_2$. 2 table must being **union compatible**. |
| Cartesian/Cross Product (乘積運算) | $R_1 \times R_2$ | Taking the cross product of two relations essentially taking every combination of the two tables’ tuples. | SELECT * FROM **CUSTOMERS, ORDERS** |
| Select (選擇運算) | $\sigma_{condition}(R)$ |  | `WHERE` |
| Project (投影運算) | $\pi_{attributes}(R)$ |  | SELECT `{attributes}` FROM ... |
| Join (關聯運算) | $R_1 \Join_{condition} R_2$ |  | `JOIN` |
| Divide (除法運算) | $R_1 \div R_2$ |  |
| Grouping | $\Im_\text{calculate(attribute)}(R)$ | | `GROUP BY` |

<details><summary>Relational Join Operation </summary>

### Relational Join Operation 
- A Join operation combines related tuples from different relations, if and only if a given join condition is satisfied. It is denoted by ⋈.
- 中: join 操作組合來自不同關係的且滿足給定連接條件的 tuple, 註為⋈
</details>
<details><summary>Cross Product Examples</summary>

### Example of Cross Product 
![](https://i.imgur.com/MDcrf3i.png)
</details>

<details><summary>Union compatibility</summary>

### Union compatibility
| Conditions | Meaning |
|-|-|
| **Same Degree:** |  兩個關聯表R1 與 R2 的屬性集必須具有相同的維度(Degree)，也就是屬性數目必須相同(n=m)。 |
| **Same Domain:** | 兩個關聯表 R1 與 R2 的相對屬性都必須定義於相同的值域 (Domain) 上。 |

滿足上述兩者條件即符合 Union compatibility
</details>