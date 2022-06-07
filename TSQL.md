# TSQL

[SQL to remove rows with duplicated value while keeping one](https://stackoverflow.com/questions/23495734/sql-to-remove-rows-with-duplicated-value-while-keeping-one)

```sql
WITH CTE AS (SELECT *, RN=ROW_NUMBER() OVER(PARTITION BY data, value ORDER BY id) FROM TableName)
DELETE FROM CTE WHERE RN>1
```
