[[STRING]]
***Concatenate:** Joining things together, like sticking two pieces of text side by side. In SQL, you use it to combine values.*

*Example: Concatenating "Hello" and "World" gives you "HelloWorld".*

***Truncate:** Cutting something off or shortening it by removing part of it. In SQL, it usually means either:*

1. *Cutting text to a specific length*
2. *Deleting all rows from a table (while keeping the table structure)*

*Example: Truncating "Elephant" to 3 characters gives you "Ele".*

Concat strings together - meaning putting strings together
so here we concat the first name ' ' and last name AS full_name

![[Pasted image 20250422114333.png]]
another way in postgres
![[Pasted image 20250422114508.png]]
using non string 
![[Pasted image 20250422114526.png]]
upper() - uppercase
lower() - lowercase
initcap() - first letter of the word would be capital
reverese() - reversing a word


![[Pasted image 20250422114720.png]]
replace strings

![[Pasted image 20250422115458.png]]
char_length 
length - they both return the length of the string

![[Pasted image 20250422115558.png]]
position -  is to find where that character is
strpos - same lang pero iba syntax
![[Pasted image 20250422115627.png]]

left - irereturn lang yung first number sa left so if 50, first 50 babalik
right - same lang pero sa right
![[Pasted image 20250422115743.png]]

substring - parang left and right
![[Pasted image 20250422115837.png]]
ganto syntax nya
`substring(column, san mag sstart, ilan characters lang)`

![[Pasted image 20250422115938.png]]

![[Pasted image 20250422120020.png]]

TRIM - usually used to remove whitespace
LTRIM 
RTRIM

![[Pasted image 20250422125213.png]]
![[Pasted image 20250422125235.png]]

LPAD - naglalagay ka ng characters
RPAD
![[Pasted image 20250422125409.png]]

![[Pasted image 20250422125342.png]]

![[Pasted image 20250422125603.png]]
naglalagay ng whitespace sa after ng first name tapos nag cconcat or pinagssama yung last_name