# Proprietary 
| Proprietary | Definition | Note |
|-|-|-|
| `Parametric End Users` | `Parametric End Users` are the unsophisticated(樸實無華) who don't have any DBMS knowledge but they frequently use the database applications in their daily life to get the desired results. For examples, Railway's ticket booking users are naive users. </br>(中：不具有DBMS相關知識但經常使用資料庫為基礎的應用程式的用戶) |
| `Views` | A database view is **a subset of a database and is based on a query** that runs on one or more database tables. </br> (中： View是基於 query 資料庫的子集) |
| `Support of mutiple views of the data` | - Each user may see a different view of the database, which describes only the data of interest to that user </br> - It may also contain some **virtual data that is derived from the database files but its not explicitly stored**. </br> (中：每個用戶都擁有各自的資料庫視圖。且可能含有由資料庫內資料所推導出來的虛擬資料) |
| `Program-data independence` | The ability to modify the scheme without affecting the programs and the application to be rewritten. </br> Data is separated from the programs, so that the changes made to the data will **not affect the program execution and the application**. </br> (中：對數據做的改變不會影響應用的執行) |
| `Impedance mismatch` | 由於 Database 上的 data model 和程式語言的 data model 不相符合，無法 匹配所引發的問題 |
| `Cascading rollback` | 某筆交易的 rollback 可能會影響到其他交易也要跟著 rollback 的現象 |
| `Serializabitlity` | 可序列化排程. 一個具有 n 筆交易的排程 與相同的 n 筆交易所構成之某一序列(Serial)排程等價(Equivalent) |
| `Write-ahead log` | The log entry must be flushed to disk before `BFIM` is overwritten with `AFIM`. |
| `Two-phase locking protocol` | 每一個交易中所有的鎖定動作，必須在所有解除鎖定動作之前。 在交易完成之前，皆保有該交易所需要的鎖定。 兩個 `Phase` 分別為 `growing phase` 與 `shrinking phase` |
| `Time stamping protocol` | 透過交易開始點的時間戳，讓交易的交錯執行擁有順序性 |
| `Optimistic concurrency protocol` | 假設所有交易皆可順利且正確地進行，因此在交易執行過程中不需要作任何的檢查動作 |
| `Shadow paging recovery protocol` | 當交易進行時，若要更新資料庫中的某一磁碟分頁的資料時，會先將要更新得值另外存放到新的磁碟分頁上，而不是直接覆蓋舊磁碟分頁的資料 |
| `Normalization`| Normalization is a database design technique that reduces `data redundancy` and eliminates undesirable `anamalies`. | [✓](./normalization.md) | 


<details><summary>Use Wait-Die and Wound-Wait to prevent deadlock and avoid starvation </summary>

### Use `Wait-die` and `Wound-wait` to prevent `deadlock` and avoid `starvation`
| Proprietary | Definition |
|-|-|
| `Deadlock` | It's an undesired situation in which two or more transactions have to wait indefinitely for each other in order to get terminated, but none of the transactions is willing to give up the allocated CPU and memory resources that the other one needs. |
| `Starvation` | `Starvation` occurs if a process is `indefinitely postponed`. This may happen if the process requires a resource for execution that it is never alloted or if the process is never provided the processor for some reason. |
| `Wait-Die` | 較早進入的交易可等待，較晚進入的交易被撤回。 <br> 假設 ${TS}_1 < {TS}_2$，表示 ${TS}_1$ 是發生在 ${TS}_2$ 之前，那麼當 ${TS}_1$ 要使用 ${TS}_2$ 已經鎖定的資料時，則允許 ${TS}_1$ 繼續等待。 相反的，假設 ${TS}_2$ 要 ${TS}_1$ 已經鎖定的資料時，則 $TS_2$ 必須立即中止執行而死亡，之後再以相同的交易時間戳重新啟動執行以避免`Starvation`問題產生。 |
| `Wound-Wait` | 較早進入的交易可搶較晚進入交易之資源，而較晚進入的交易則需等待。 <br>  假設 ${TS}_1 < {TS}_2$，表示 ${TS}_1$ 是發生在 ${TS}_2$ 之前。則 ${TS}_1$ 要使用 ${TS}_2$ 鎖定的資料時，則${TS}_2$ 必須立即中止執行，而後再以相同時間戳重新啟動執行，從而避免 `Starvation` 產生。相反地，假設 ${TS}_2$ 要使用 ${TS}_1$ 已經鎖定的資料時，則 ${TS_2}$ 必須繼續等待 |
</details>

