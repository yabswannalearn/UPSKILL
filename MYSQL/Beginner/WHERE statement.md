`where statement  is used to extract only those records that fulfill a specified _condition_. It is like the IF in python.

```
SELECT *
FROM employee_salary
WHERE salary <= 50000
;

```

you can also use AND, OR ,NOT

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


you can use the [[LIKE statement]] in with WHERE
and WHERE and [[HAVING statement]] can be together too

example code:
```
SELECT occupation, AVG(salary)
FROM employee_salary
WHERE occupation LIKE '%manager%'
GROUP BY occupation
HAVING AVG(salary) > 75000
;
 
```

**<> = not equal to**

![[Pasted image 20250307210731.png]]

![[Pasted image 20250307214255.png]]
add a parenthesis when using AND and OR

LIKE use % for to find any words with that letter for example t% 
![[Pasted image 20250308081554.png]]

NOT LIKE use % for to find any words with that letter for example t% 

IN can use in finding multiple words or dates
![[Pasted image 20250308082354.png]]



[[JOINS statement#^innerjoin |INNER JOIN]]

[[JOINS statement#^self-join |SELF JOIN]]
