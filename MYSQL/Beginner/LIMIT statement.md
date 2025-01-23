pwedeng gamitin ang limit para ma limit mo ang output.
so if ssabihin mo ```limit 3``` ang top 3 lang ang llitaw.

pwede sya ma combine with [[ORDER BY keyword]] 

```
SELECT *
FROM employee_demographics
ORDER BY age DESC
LIMIT 2, 1
;
```
ang unang number sa limit ay kung saan mag sstart, tapos yung pangalawa doon sya magbbilang tapos ganon lang kadami ang output nya