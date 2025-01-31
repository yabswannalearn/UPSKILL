There are INNER JOIN and OUTER JOIN, they join together columns

[[JOINS statement#^innnerjoin|INNER JOIN]] ay pinagssama ioutput from different tables

iooutput lang din kapag magka parehas silang data

example:

```
SELECT dem.employee_id, age, occupation
FROM employee_demographics AS dem
INNER JOIN employee_salary AS  sal
	ON dem.employee_id = sal.employee_id
;

```

sa code na to pinagsama yung columns ng demographic at salary, dem.employee naman ay ginamit para malaman kung saang table sya kkuha ng data

ginamit din ang [[ALIASING statement]] para mas madaling basahin ang code.

[[JOINS statement#^left_join |LEFT JOIN]] - inooutput nya from left to right table

```
 SELECT *
FROM employee_demographics AS dem
LEFT JOIN employee_salary AS  sal
	ON dem.employee_id = sal.employee_id
;
```

sa code na to ang left table ay ang employee_demographics and ang right naman ay ang employee_salary


[[JOINS statement#^right-join|RIGHT JOIN]] - inooutput nya from right to left

sa parehas na join na to if meron data na hindi parehas ppopulate nya as null

example output:
![[Pasted image 20250124164838.png]]

[[JOINS statement#^self-join |SELF JOIN]] 

you can use SELF JOIN to join a table by itself

example code:

```
SELECT emp1.employee_id AS emp_santa,
emp1.first_name AS first_name_santa,
emp1.last_name AS last_name_santa,
emp2.employee_id AS emp_name,
emp2.first_name AS first_name,
emp2.last_name AS last_name
FROM employee_salary emp1
JOIN employee_salary emp2
	ON  emp1.employee_id + 1 = emp2.employee_id
;
```

in this code we SELF JOIN the employee_salary table to choose a secret santa, we added 1 to the employee id and the left table is the secret santa

JOINING MULTIPLE TABLES TOGETHER
you can join multiple tables together

this code joins the demographics into salary and the salary into parks_department to get the department id

```
SELECT *
FROM employee_demographics AS dem
INNER JOIN employee_salary AS  sal
	ON dem.employee_id = sal.employee_id
INNER JOIN parks_departments AS pd
	ON sal.dept_id = pd.department_id
;

```