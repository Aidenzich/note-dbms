# 2022 Final 考古
## SQL題
### AVG, GROUP, HAVING
```SQL
SELECT S.SID, AVG(T.Score)
FROM Student as S, Take as T
WHERE S.SID = T.SID
GROUP BY S.SID
HAVING S.AVG < 18;
```

### Subquery
- 這邊乾脆用join... 用子查詢加乘積運算也太慢 lol
```SQL
SELECT C.Title, T.Name 
FROM Course AS C, Take AS K, Teacher AS T 
WHERE C.CID IN (
    SELECT K.CID FROM Take as K, Teacher as T, Stustent as S WHERE K.TID = T.TID and K.SID = S.SID and S.Age > T.Age 
    GROUP BY K.CID, K.TID
    HAVING COUNT(*) > 5
) AND C.CID = K.CID and K.TID = T.TID;
```

### 
```SQL
SELCT C.Title, T.Name, COUNT(*) 
FROM Course AS C AND
Take AS K AND
Teacher AS T 
WHERE C.CID in (
    SELECT C.CID 
    FROM Take AS K, Course AS C 
    WHERE C.credit = 3 AND K.CID = C.CID
    GROUP BY C.CID
    HAVING COUNT(*) > 50
) and C.CID = K.CID and K.score > 95 and T.TID=K.TID 
GROUP BY C.CID
```


### 推 2NF 跟 3NF
- Relation is 
    $$
    R(A, B, C, D, E, F, G, H, I, J)
    $$
- Functional Dependencies is 
    $$
    A, B \rightarrow C, D, E, F, G, H, I, J \\
    A \rightarrow I \\
    B \rightarrow J \\
    D \rightarrow E, F \\
    F \rightarrow G, H \\
    $$

#### ANS
- 2NF
    $$
    R_1(A, B, C, D, E, F, G, H) \\
    R_2(A, I) \\
    R_3(B, J)
    $$
- 3NF
    $$
    R_1(A, B, D) \\
    R_1(D, E, F) \\
    R_2(F, G, H) \\
    R_3(A, I) \\
    R_4(B, J)
    $$

