Distinct is for returning the same values

so if all of the tables have "female" in the column
it will only return "female".

```
SELECT DISTINCT age + 10 #you can add
FROM (what data base you are using).(what tables u are using);
```

pwede mo sya pagsama with [[ORDER BY keyword]] and [[LIMIT statement]]

```
SELECT DISTINCT age
FROM parks_and_recreation.employee_demographics
order by age desc
LIMIT 5
;
```

pwede mo rin sya ipagsama with [[ALIASING statement]] para mapalitan ang column name, parang ganito

```
SELECT DISTINCT age as egg
FROM parks_and_recreation.employee_demographics
order by egg desc
LIMIT 5
;
```
