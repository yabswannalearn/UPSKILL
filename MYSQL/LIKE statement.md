The `LIKE` operator is used in a `WHERE` clause to search for a specified pattern in a column.

There are two wildcards often used in conjunction with the `LIKE` operator:

-  The percent sign `%` represents zero, one, or multiple characters
-  The underscore sign `_` represents one, single character

sa % basta meron syang ganong letter or number makkuha na

sa _ ganon na ganon lang sya

```
SELECT *
FROM employee_demographics
WHERE first_name LIKE '%r%'
;

SELECT *
FROM employee_demographics
WHERE first_name LIKE 'a___%'
;

SELECT *
FROM employee_demographics
WHERE birth_date LIKE '198%'
;
```