pinag ssama nya mga data sa iisang column

```
SELECT first_name, last_name,
CONCAT(first_name, ' ' , last_name) AS full_name
FROM employee_demographics;
```

sa code na to ginamit ang [[ALIASING statement]] para ang output ay full_name na column