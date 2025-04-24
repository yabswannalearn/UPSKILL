eto ang totoong if else

use case statements pra sa multiple if else

example code:

```
SELECT first_name,
last_name,
age,
CASE 
	WHEN age <= 30 THEN 'YOUNG' 
    WHEN age FBETWEEN 31 and 50 THEN 'OLD'
    WHEN age >= 50 THEN 'mamamatay kna'
END AS AGE_BRACKET
FROM employee_demographics;
```

maglagay ng [[ALIASING statement]] sa END ng CASE statement

U CAN USE MULTIPLE CASES IN A [[SELECT statement]]

```
SELECT first_name,
last_name, 
salary,
CASE
	WHEN SALARY < 50000 THEN salary + (salary * 0.05)
    WHEN SALARY > 50000 THEN SALARY + (SALARY * 0.07)
END AS NEW_SALARY,
CASE
	WHEN dept_id = 6 THEN SALARY + (SALARY* 0.10)  
END AS BONUS
from employee_salary;

```