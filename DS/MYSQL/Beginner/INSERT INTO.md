ginagamit to para magpasok ng new records sa loob ng table

1. Specify both the column names and the values to be inserted:

```
INSERT INTO _table_name_ (_column1_, _column2_, _column3_, ...)  
VALUES (_value1_, _value2_, _value3_, ...);
```

1. 2. If you are adding values for all the columns of the table, you do not need to specify the column names in the SQL query. However, make sure the order of the values is in the same order as the columns in the table. Here, the `INSERT INTO` syntax would be as follows:
```
INSERT INTO _table_name_  
VALUES (_value1_, _value2_, _value3_, ...);
```