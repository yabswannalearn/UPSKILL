The `ORDER BY` keyword is used to sort the result-set in ascending or descending order.

ang pag lagay ng column ay importante, for example if nauna mong nilagay ang age (which is usually almost laging unique) hindi na icconsider ang gender.

dapat ganito:
```
-- ORDER BY
SELECT *
FROM employee_demographics
ORDER BY gender, age DESC
;
```

