LENGTH - counts the number of letters in the word
```
SELECT first_name, length(first_name)
FROM employee_demographics
ORDER BY 2;
```

UPPER - caps lock the words
LOWERR - small the words
```
SELECT UPPER('sky');
SELECT LOWER('SKY');
```


TRIM - cleans the space inside of a ' ' (i forgot what to call this)
LTRIM - LEFT TRIM
RTRIM - RIGHT TRIM

LEFT - only outputs the number that you pre determined 
example:
```
SELECT first_name, LEFT(first_name, 4)
FROM employee_demographics;
```
output is the only first 4 letter of the first name

RIGHT - only outputs the last number letter of the word
```
SELECT first_name,
LEFT(first_name, 4),
RIGHT(first_name, 4)
FROM employee_demographics;

```
the output of the right is if we have a name of 'reinael' the output is 'nael'

SUBSTRING - it can start from the first number you give it and counts starting from there
```
SELECT first_name,
LEFT(first_name, 4),
RIGHT(first_name, 4),
SUBSTRING(first_name,3,2)
FROM employee_demographics;
```

starts counting at letter 3 and only outputs 2 letters after that

REPLACE