# What is Normalization in DBMS?
Normalization is a database design technique that reduces `data redundancy` and eliminates undesirable `anamalies`.

## What is the purpose of Normalization?
沒有正規化會造成：
- 容易有資料重覆儲存的浪費情形
- 資料在做插入、刪除或更新動作時產生異常情形

正規化的目的：
- 降低 `資料重覆性 Data Redundancy`
- 避免產生插入、刪除或更新可能的 `異常 Anamalies`

##  Database Normal Forms
| Form | Definition |
|-|-|
| `2 Normal Form` | 一個關聯表為 `2NF`，若且唯若關聯表中，所有非鍵值屬性皆完全功能相依於主鍵 ，且關聯表滿足 1NF |
| `3 Normal Form` | 一個關聯表為 `3NF` ，若且唯若關聯表中不存在非鍵值屬性遞移 相依於主鍵，且關聯表滿足 2NF |
| `Boyce-Codd Normal Form, BCNF` | 一個關聯表為 `BCNF` ，若且唯若關聯表中， 所有的功能 相依 性之決定因素都是 `Superkey`，且關聯表滿足 2NF，比 3NF 更加嚴謹 |