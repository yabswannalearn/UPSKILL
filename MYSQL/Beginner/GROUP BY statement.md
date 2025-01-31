The `GROUP BY` statement groups rows that have the same values into summary rows, like "find the number of customers in each country".

The `GROUP BY` statement is often used with aggregate functions (`COUNT()`, `MAX()`, `MIN()`, `SUM()`, `AVG()`) to group the result-set by one or more columns.

sa group by kung ano lang ang tinawag mo ay yun lang ang lalabas sa output. so for example tinawag mo lang ay occupation, yon lang ang lalabas.

```
SELECT gender, AVG(age), MAX(age), MIN(age), COUNT(age)
FROM employee_demographics
GROUP BY gender
;
```

```
SELECT occupation, salary
FROM employee_salary
GROUP BY occupation, salary
;
```

kung ttawagin mo sya sa [[SELECT statement]] (aggregate) dapat ilagay mo rin sya sa GROUP BY.

tapos if 10 ang tao (5 males) (5 females), tapos iccall mo ang male and female, ang output ay dalawa lang which is male and female.


count bbilangin kung ilan