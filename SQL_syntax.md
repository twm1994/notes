### pattern matching
```sql
LIKE/NOT LIKE 'pattern'
_ -> match any single character
% -> match an arbitrary number of characters
REGEXP_LIKE(,)/REGEXP/RLIKE
```

### keyword
```sql
DISTINCT
ORDER BY
DESC
INTERVAL
GROUP BY
IS
IS NOT
table1 INNER JOIN table2 ON
LIMIT
AUTO_INCREMENT
```

### function
```sql
TIMESTAMPDIFF(YEAR/MONTH/DAY,,)
CURDATE()
DATE_ADD()
COUNT(*)
MAX()
```

### load records to table
`LOAD DATA LOCAL INFILE 'filename' INTO TABLE tablename;`

```sql
LOAD DATA INFILE '/home/export_file.csv'
INTO TABLE table_name
FIELDS TERMINATED BY ','
ENCLOSED BY '"'
LINES TERMINATED BY '/n'
-- '\r\n' on Windows?
IGNORE 1 ROWS;
```

### find data directory
`mysql> select @@datadir;`

### rename
`ALTER TABLE old_table_name RENAME new_table_name;`

### get database and table information
```sql
SELECT DATABASE();
SHOW TABLES;
DESCRIBE tablename;
```

### batch mode
`mysql -h host -u user -p < batch-file`
