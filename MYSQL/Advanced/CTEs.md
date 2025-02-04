cte = common table expression
using cte  u need to use WITH cluase followed by a parenthesis

para syang subquerry pero mas madaling basahin at intidihin yung syntax nya
example code:

```
WITH CTE_EXAMPLE AS
(
SELECT gender,
avg(salary) avg_sal,
max(salary) max_sal, 
min(salary) min_sal, 
count(salary) count_sal
from employee_demographics dem
join employee_salary sal
	on dem.employee_id = sal.employee_id
group by gender
)
select avg(avg_sal)
from cte_example
;

```

pwede mo lang sya gamitin kapag ginawa mo na sya, so parang hindi sya pwede sa kabilang code block 

```
WITH CTE_EXAMPLE (GENDER, AVG_SAL, MAX_SAL, MIN_SAL, COUNT_SAL) AS 
(
SELECT gender,
avg(salary) avg_sal,
max(salary) max_sal, 
min(salary) min_sal, 
count(salary) count_sal
from employee_demographics dem
join employee_salary sal
	on dem.employee_id = sal.employee_id
group by gender
)
select avg(avg_sal)
from cte_example
;
```

as u can see na hindi mo na need gumamit ng [[ALIASING statement]] para ma rename mo yung [[SELECT statement]] mo if gumagamit ka ng CTEs, pero parang mas prefer ko [[ALIASING statement]] hehe.

gumamit ka ng [[GROUP BY statement]], [[ALIASING statement]] and [[JOINS statement]] para dito

```
WITH CTE_EXAMPLE AS
(
SELECT employee_id, gender, birth_date
from employee_demographics
where birth_date > '1985-01-01'
),
cte_example2 as
(
select employee_id, salary
from employee_salary
where salary > 50000
)
select *
from cte_example
join cte_example2
	on cte_example.employee_id = cte_example2.employee_id
;
```

dito naman meron kang [[WHERE statement]]. gumamit ka ng dalawang cte para ma combine mo sila using [[JOINS statement]]