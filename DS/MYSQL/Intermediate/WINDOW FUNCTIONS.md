para syang [[GROUP BY statement]] pero mas malakas ata to hahah

ginagamit to para sa maging mas madali yung output: example code:
```
SELECT gender, avg(SALARY) OVER()
FROM employee_demographics dem
JOIN employee_salary sal
	ON dem.employee_id = sal.employee_id
;

```

OVER() meaning lahat
```
SELECT gender, avg(SALARY) OVER(PARTITION BY gender)
FROM employee_demographics dem
JOIN employee_salary sal
	ON dem.employee_id = sal.employee_id
;
```

PARTITION BY meaning hinahati

```
SELECT dem.first_name, dem.last_name, gender, avg(SALARY) OVER(PARTITION BY gender)
FROM employee_demographics dem
JOIN employee_salary sal
	ON dem.employee_id = sal.employee_id
;

```
sa code na to iisa parin yung output na avg, compared sa group by na mag iiba lahat

```
SELECT dem.first_name, dem.last_name, gender, salary,
SUM(salary) OVER(PARTITION BY gender ORDER BY dem.employee_id) AS ROLLING_TOTAL
FROM employee_demographics dem
JOIN employee_salary sal
	ON dem.employee_id = sal.employee_id
;

```

we used [[ORDER BY keyword]] to make a rolling total
rolling total ipag add yung first number sa kasunod parang yung sa econ na inaral natin non

gumagamit din ng [[ALIASING statement]] para hindi mahirapan sa pangalan

```
SELECT dem.employee_id, dem.first_name, dem.last_name, gender, salary,
row_number() OVER(PARTITION BY gender)
FROM employee_demographics dem
JOIN employee_salary sal
	ON dem.employee_id = sal.employee_id
;

```

sa code na to gumamit tayo ng row_number para mabilang yung rows tapos over() na may partition by gender para mahati sa gender yung pagbbilang

```
SELECT dem.employee_id, dem.first_name, dem.last_name, gender, salary,
row_number() OVER(PARTITION BY gender order by salary asc)
FROM employee_demographics dem
JOIN employee_salary sal
	ON dem.employee_id = sal.employee_id
;

```
gumamit ng order by dito para yung output maging from lowest na salary pataas

```
SELECT dem.employee_id, dem.first_name, dem.last_name, gender, salary,
row_number() OVER(PARTITION BY gender order by salary desc) AS row_num,
RANK() OVER(PARTITION BY gender order by salary desc) as row_rank
FROM employee_demographics dem
JOIN employee_salary sal
	ON dem.employee_id = sal.employee_id
;

```

here we used rank() para syang row() pero iiskip nya yung same details = same number pero it will keep counting based on its position

```
SELECT dem.employee_id, dem.first_name, dem.last_name, gender, salary,
row_number() OVER(PARTITION BY gender order by salary desc) AS row_num,
RANK() OVER(PARTITION BY gender order by salary desc) as row_rank
DENSE_RANK() OVER(PARTITION BY gender ORDER BY salary DESC) dense_rank_num
FROM employee_demographics dem
JOIN employee_salary sal
	ON dem.employee_id = sal.employee_id
;

```

in this code we have DENSE_RANK() kung saan kapag nag unlike sa rank() which pag nag duplicate ay ttuloy lang sa pagbilang, dito naman mag ddoble tapos mag bbilang ng kasunod na number. example is if duplicate ang 5 next row ay 6 na. sa RANK() kasi ay pag nag duplicat ang 5, next number ay 7 na

https://www.youtube.com/watch?v=rIcB4zMYMas
great yt vid tutorial

PAGING
NTILE()

![[Pasted image 20250418120411.png]]

![[Pasted image 20250418120436.png]]

![[Pasted image 20250418120455.png]]

using window function with aggregate functions:
![[Pasted image 20250418122159.png]]
![[Pasted image 20250418122204.png]]
and with partition by
![[Pasted image 20250418122216.png]]

FRAMES:

`RANGE BETWEEN UNBOUNDED PRECEDING AND UNBOUNDED FOLLOWING`

