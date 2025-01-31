UNIONS pinagssama mga rows sa isang column

UNIONS DISTINCT - removes duplicate rows

UNION ALL - puts together all, even if they are duplicate

``
```
SELECT first_name, last_name, 'Old Man' as label
FROM employee_demographics
WHERE age > 40 AND gender = 'Male'
UNION SELECT first_name, last_name, 'Old Female' as label
FROM employee_demographics
WHERE age > 40 AND gender = 'Female'
UNION 
SELECT first_name, last_name, 'High' as label
FROM employee_salary
WHERE salary > 70000
ORDER BY first_name, last_name
;
```

in this code we used 3 union, first and second are from the demographics to get if they are old man or old woman and third is from the salary, if they have a salary larger than 70,000

we used the [[WHERE statement]] to get the IF statements and [[ORDER BY keyword]] to easily see them  