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

### 
```SQL
SELECT C.Title, T.Name 
FROM Course as C, Take as K, Teacher as T 
WHERE C.CID in (
    SELECT K.CID FROM Take as K, Teacher as T, Stustent as S WHERE K.TID = T.TID and K.SID = S.SID and S.Age > T.Age 
    GROUP BY K.CID, K.TID
    HAVING COUNT(*) > 5
    ) 
```