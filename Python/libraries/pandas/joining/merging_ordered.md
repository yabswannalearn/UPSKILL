it looks like [[outer join]], but it is ordered
![[Pasted image 20250523221121.png]]
difference with merge ([[INNER JOIN]])
![[Pasted image 20250523221255.png]]

how to do it
![[Pasted image 20250523221437.png]]
syntax is like this
```
pd.merge_ordered(table1, table2, on, suffixes)
```
filling the null or NaN values
![[Pasted image 20250523221519.png]]
how to forward fill
![[Pasted image 20250523221559.png]]
here are the comparisons
![[Pasted image 20250523221613.png]]
when to use merge_ordered?
![[Pasted image 20250523221649.png]]
