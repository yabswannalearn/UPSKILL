parang [[merging_ordered]]

less than or equal to
![[Pasted image 20250525073604.png]]
so as you can see, the closest to B3 5 is 3 D3, that's why it was merged. same goes with B4 and 7 D7.

syntax:
![[Pasted image 20250525073741.png]]
 using forward
 ![[Pasted image 20250525073926.png]]
more examples:
![[Pasted image 20250525074238.png]]
```
so in this merge, you merged on time, for example in the row 1 the time are 10:00 and 9:59, since 9:59 is less than 10:00, it will be merged to that row
```
![[Pasted image 20250525074303.png]]
![[Pasted image 20250525075608.png]]
we are merging
using [[list comprehension]]
and [[plot]], specifically, [[Bar plots]]

simple explanation of this code:
### 📌 What it does:

1. **`merge_asof()`** joins `gdp` with the nearest `recession` status by date.
    
2. **Creates color list**: `'r'` for recession, `'g'` for growth.
    
3. **Plots a bar chart**:
    
    - X = date
        
    - Y = GDP
        
    - Color = red or green based on recession
