## ER Diagram
![](https://i.imgur.com/k21qH3o.png)

| Term | Symbol | Note |
|-|-|-|
| **Entity Type** | ![](https://i.imgur.com/deERxaT.png) | A `table`  | 
| **Weak Entity Type** | ![](https://i.imgur.com/AP3XKQr.png) | - 無法獨立存在的 `table` , 必須依賴另一個實體存在 </br> - 例如 `order` 與 `order_items` 之間的關係 |
| **Relationship Type** | ![](https://i.imgur.com/MrMmnjh.png) | - 代表兩個以上Entity之間的關係 |
| **Total Participation** | ![](https://i.imgur.com/yJyRmnA.png) | - Entity Set 內的每一個 Entity 都一定存在有這樣的關係，例如：每個員工都需對應一個部門 |
| **Partial Participation**  | 見以下2種 | 非 total participation 的關係 |
| Cardinality(基數) Ratio 1:N | ![](https://i.imgur.com/4NeDOKt.png) |     - 每一個 Employee 最多有一個 WorksFor 的關係, 因為一個員工只能隸屬於一個部門, Department 則可有多個 WorksFor 的關係, 因為一個部門可以有多個員工. 圖左員工右部門 |
| Structural Constraint (min, max) | ![](https://i.imgur.com/UDv3K8Q.png) | - 指一個實體最少有 `min` 個最多有 `max` 個關係. 如假設一個部門最少有四個員工, 則 Department 和 WorksFor 之間的 Structure Constraint 為(4,N). |
| **Identifying Relationship Type** | ![](https://i.imgur.com/G1dCCjO.png) | - `Weak Entity Type` 所依附的 `Entity Type` 的實體稱為 `identifying owner`, 兩個Entity Type 間的關係即 **identifying relationship**. |
| **Attribute** | ![](https://i.imgur.com/zsnqmyG.png) | - table's `column` |
| **Key Attribute** | ![](https://i.imgur.com/LI7Vt5S.png) | - 若該 column 為 key, 以 underline 標記 |
| Partially unique key attribute | ![](https://i.imgur.com/D5YURVo.png) | The dotted line means that it is **PARTIALLY unique**. ie: if the database if for apartment buildings, the apartment numbers would be partially unique because they are only unique in said apartment but reused in different buildings. |
| **Multivalued Attribute** | ![](https://i.imgur.com/5XSukND.png) | - 指這個屬性有多個值, 如一個人可以有多個嗜號, 因此hobby這個屬性的值可為 "籃球,壘球,看電影". |
| **Composite Attribute** | ![](https://i.imgur.com/fgeoj8G.png) | - 指這個屬性可細分為多個子屬性, 如 Address 可分為 Street,State,Zip Code,Country 等部份. Name 可分為 First Name, Middle Name, Last Name 等部份. |
| **Derived Attribute** | ![](https://i.imgur.com/6zdFkIl.png) | - 屬性的值是由其它屬性計算出來的,本身並不存在. </br> 如 Corporation 這個 Entity Type 可以有 NumberOfEmployee 這個屬性, 但這個屬性的值是由Employee這個 Entity 目前的 Entity Set 內的實體數目所決定, 因此可以把 NumberOfEmployee 這個屬性視為 Derived Attribute. |
