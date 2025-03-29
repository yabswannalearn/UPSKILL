querry sa loob ng querry


```
select *
from employee_demographics
WHERE employee_id IN 
					(SELECT employee_id
						FROM employee_salary
						WHERE dept_id = 1 )
;

```

using subquerries with [[WHERE statement]]

```
select avg(max_age), avg(min_age), avg(count_age)
from
(select gender, 
avg(age) as avg_age,
max(age) as max_age,
min(age) as min_age, 
count(age) as count_age
from employee_demographics
group by gender) as agg_table
;

```
in this code we used [[GROUP BY statement]] kung san merong select table sa loob ng select table para ma output yung average ng average na kinuha natin sa loob ng unang select

tangina sana gets mo sa future amen ako kasi ngayon di ko HAHAHAHHA