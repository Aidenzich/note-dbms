## Relational Integrity Constraints
Constraints are **conditions that must hold on all valid relation instances**. There are three main types of constraints.
1. **Key Constraints**
    - **Superkey**
        - for any distinct tuples t1 & t2, t1's superkey $\neq$ t2's superkey.
        - 中：實體內的tuple間的 superkey 值需要有唯一性，不可重複
    - **Key**
        - The **minimal** superkey. A superkey that combines two attributes is not a Key.
        - 中：superkey 只有一個 `attribute`，則該 attribute 為 key 值; 由多個 `attributes` 組成
    - If a relation has several candidate keys, one is chosen arbitrarily to be the primary key. The primary key attributes are underlined.
2. **Entity Integrity**
    - The primary key **cannot have null values** in any tuple of $R$.
    - (Note) integrity: the state of being whole and undivided.
3. **Referential Integrity**
    - Tuples in the $R_1$ have attributes **Foreign Key** that reference the **Primary Key** attributes.
