

The `HAVING` clause was added to SQL because the [[WHERE statement]] keyword cannot be used with aggregate functions.

HAVING comes after [[GROUP BY statement]] 

```
SELECT occupation, AVG(salary)
FROM employee_salary
GROUP BY occupation
HAVING AVG(salary) > 75000
;
```

you can also use having and where at the same time. 
like this:

```
SELECT occupation, AVG(salary)
FROM employee_salary
WHERE occupation LIKE '%manager%'
GROUP BY occupation
HAVING AVG(salary) > 75000
;
```