# unix time to readable time

使用方法 `FROM_UNIXTIME`

第一個參數：`unix time`

第二個參數：`format`（可選）

```sql
-- 2021-09-01 23:09:26
SELECT FROM_UNIXTIME(1630508966)

-- 202109012309
SELECT FROM_UNIXTIME(1630508966, '%Y%m%d%H%i')
```
