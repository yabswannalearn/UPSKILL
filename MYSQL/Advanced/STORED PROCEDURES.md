its like a function in python where you can put codes inside and then call it for later use

so to create a stored procedure you have to 'CREATE PROCEDURE' then the name then the parenthesis afterwards

example code:

```
CREATE PROCEDURE large_salaries()
SELECT *
FROM employee_salary
WHERE salary >= 50000;

```

and if you want to call it you're going have to 'CALL' then the name along with the parenthesis

```
CALL large_salaries();
```

gumamit tayo ng [[WHERE statement]] para sa code na to


if you want to put complex codes inside a store procedure you're going to have to use a delimiter

delimiter tells sql that kung ano lang yung issali sa stored procedure na yun
so llagyan mo ng begin and end

example code

```
DELIMITER $$
CREATE PROCEDURE large_salaries2()
BEGIN
	SELECT *
	FROM employee_salary
	WHERE salary >= 50000;
	SELECT *
	FROM employee_salary
	WHERE salary >= 10000;
END $$

```

so dito naglagay ng delimiter para malaman kung hanggang saan at ano ang kasama sa stored procedure na yun. lagay ka ng $ $ after word na delimiter at after ng end  $ $

or if ayaw mo mag type ng ganyan, pwede ka namang mag right click sa stored procedures sa right and lagay mo ng new procedures, then type mo code and apply which is nasa left


kung gusto mo naman na specific lang ang makuha mo sa procedures na to pwede ka lang lagay ng parameters
parameters ay ginagamit para maging specific

so eto example code para mas gets mo/

```
DELIMITER $$
CREATE PROCEDURE large_salaries4(employee_id_param INT)
BEGIN
	SELECT salary
	FROM employee_salary
	WHERE employee_id = employee_id_param
    ;
	
END $$
```
so dito naglagay ka ng parameter na employee id tapos lagyan mo ng variable if string or int ba yung gusto mong gamitin pag nag call ka. so dito gumamit ka ng INT kasi "1" yung gagamtiin mong pang call.
at ggamit ka ng [[WHERE statement]] para ma call mo sya
so WHERE sa employee_id = (anong param ang nilagay mo) habang nag ccreate

so kapag ccall mo na sya pwede kana mag input

```
CALL large_salaries4(1)
```
so dito nag call ka ng employee_id 1 kaya yun lang ang output