keyword of aliasing is "AS" 

aliasing ay ginagamit pang palit ng pangalan ng column

sa code na to ginamit sya with [[HAVING statement]] para pag cinall mo yung "AVG(age)" ay ccall mo nalang na "avg_age"

```
SELECT gender, AVG(age) AS avg_age
FROM employee_demographics
GROUP BY gender
HAVING avg_age > 40;
```



```
WITH duplicate_cte AS
(
SELECT *,
ROW_NUMBER() OVER(
PARTITION BY 
company,
location, 
industry,
total_laid_off, 
percentage_laid_off, 
`date`,
stage,
country,
funds_raised_millions) AS row_num
FROM layoffs_staging
)
SELECT *
FROM duplicate_cte
WHERE row_num > 1;
```