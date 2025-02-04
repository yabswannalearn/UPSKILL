ginagamit lang to para mag create ka ng temporary table na kapag nag exit ka ng session, mawwala rin yung temp table

```
CREATE TEMPORARY TABLE temp_table
```

```
-- temp table

CREATE TEMPORARY TABLE temp_table
(first_name varchar(50),
last_name varchar(50),
favorite_movie varchar(100)

);

SELECT *
from temp_table;

INSERT INTO temp_table
VALUES('REI', 'YABS', 'GREEEN BOOK' )
;

INSERT INTO temp_table
VALUES('REI2', 'HELLO', 'WORLD');

select *
from temp_table;
```

una nag create ka ng table, then chineck if gumana
nag insert ka ng value using INSERT TO and VALUES, after mo sulat yang syntax na yan i run mo para ma save sya

then check mo sa select *


another use case for temp table:

so if meron ng existing values pwede mo parin gamitin yung temp tables.
example sa code na to

```
CREATE TEMPORARY TABLE salary_over_50k
SELECT *
FROM employee_salary
WHERE salary >= 50000;

SELECT *
FROM salary_over_50k;
```

so gumawa ka ng temp table para mahiwalay mo ng table yung mga taong salary is >= 50k
