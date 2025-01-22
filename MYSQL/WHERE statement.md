where statement  is used to extract only those records that fulfill a specified _condition_. It is like the IF in python.

```
SELECT *
FROM employee_salary
WHERE salary <= 50000
;

```

you can also use AND OR NOT

```
SELECT *
FROM employee_demographics
WHERE birth_date > '1985-01-01'
AND gender = 'male'
;

SELECT *
FROM employee_demographics
WHERE birth_date > '1985-01-01'
OR NOT gender = 'male'
;
```


