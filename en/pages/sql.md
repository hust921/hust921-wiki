# SQL

## Statistics
```sql
set statistics io on
set statistics time on
```

## xml / json
```sql
for xml path;
for json path;

```

## MERGE
```sql
MERGE target_table USING source_table
ON merge_condition
WHEN MATCHED
    THEN update_statement
WHEN NOT MATCHED
    THEN insert_statement
WHEN NOT MATCHED BY SOURCE
    THEN DELETE;
```

## CHARINDEX
```sql
SELECT CHARINDEX('t', 'Customer')
-- Output: 4
```
