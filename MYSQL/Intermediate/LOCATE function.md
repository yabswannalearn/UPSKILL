it looks for what you are finding

```
SELECT first_name, LOCATE('r', first_name )
FROM employee_demographics;
```

pwede mo lagyan ng [[ALIASING statement]] sa dulo

```
SELECT occupation, locate('NURSE', occupation) as nurse
FROM employee_salary;

```

```
select first_name, last_name, department_id, dept_id, department_name, locate('FINANCE', department_name) as finding_finance
from parks_departments as park
left join employee_salary as salary
	on park.department_id = salary.dept_id
having finding_finance > 0
;
```

using [[SELECT statement]], [[JOINS statement]], and [[ALIASING statement]]  with [[LOCATE function]] to find the guy who works in finance. using [[HAVING statement]] to extract the only guy who works in finance, because [[WHERE statement]] cannot be used due to an aggregate function