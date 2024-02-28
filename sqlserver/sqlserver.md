# SQL Server
## Tables with updated rows
```
SELECT 
      [db_name] = d.name
    , [table_name] = SCHEMA_NAME(o.[schema_id]) + '.' + o.name
    , s.last_user_update
FROM sys.dm_db_index_usage_stats s
JOIN sys.databases d ON s.database_id = d.database_id
JOIN sys.objects o ON s.[object_id] = o.[object_id]
WHERE o.[type] = 'U'
    AND s.last_user_update IS NOT NULL
    order by s.last_user_update desc
```
## Update tables
```
select modify_date as sort, * from sys.tables order by sort desc
```
