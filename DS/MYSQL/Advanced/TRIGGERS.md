so kapag may na TRIGGER merong EVENT na mangyyari

to create a trigger gawa ka ng CREATE TRIGGER tapos pwede mo gawan ng AFTER or BEFORE insert on and ng FOR EACH ROW

para mag start ka ng just do a BEGIN and END

```
SELECT *
FROM employee_demographics;

SELECT *
FROM employee_salary;


DELIMITER $$
CREATE TRIGGER employee_insert
	AFTER INSERT ON employee_salary
    FOR EACH ROW 
BEGIN
	INSERT INTO employee_demographgics (employee_id, first_name, last_name)
    VALUES (NEW.employee_id, NEW.first_name, NEW.last_name);
END $$
DELIMITER ;
```
so sa code na to mag iinsert tayo ng employee id, first name, last name sa employee demographics table na galing sa employee salary table. kapag NEW bago, kapag OLD luma

kapag nag create ka na ng trigger makkita mo siya sa schema tab which is nasa left.

kapag naman gusto mo na ma try yung trigger na ginawa mo pwedeng ganito 
```
INSERT INTO employee_salary (employee_id, first_name, last_name, occupation, salary, dept_id)
VALUES(13, 'REI', 'POGI', 'DATA ANALYST', 1000000000, NULL);
```

kapag gusto mong mag tanggal ng trigger na ginawa mo since di pwedeng manual, pwede mong run to sa workbench mismo


general:
```
DROP TRIGGER [IF EXISTS] [_schema_name_.]_trigger_name_
```

specific:
```
DROP TRIGGER IF EXISTS parks_and_recreation.employee_insertt;
```