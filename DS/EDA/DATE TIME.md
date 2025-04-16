![[Pasted image 20250413190425.png]]
![[Pasted image 20250413190435.png]]


ISO STANDARD
![[Pasted image 20250413190558.png]]

UTC = COORDINATED UNIVERSAL TIME

![[Pasted image 20250413190623.png]]

OFFSET YUNG SA HULI

![[Pasted image 20250413190639.png]]

![[Pasted image 20250413190703.png]]

![[Pasted image 20250413190744.png]]

![[Pasted image 20250413191732.png]]
using the cast to add 5 minutes to the time now

FIELDS
![[Pasted image 20250413192407.png]]

EXTRACTING FIELDS
![[Pasted image 20250413192432.png]]
![[Pasted image 20250414071810.png]]

 ![[Pasted image 20250414071831.png]]
 ![[Pasted image 20250414072801.png]]
 ![[Pasted image 20250414073231.png]]
`This computer instruction looks at a list of requests called `evanston311`. It figures out which day of the week each request was started on. Then, it calculates the average time it took to finish the requests for each starting day. The results show that, on average, requests started on Sunday took about 8 days and 23 hours to complete, while requests started on Monday took about 7 days and 47 minutes to complete.`

trunc

![[Pasted image 20250414073755.png]]![[Pasted image 20250414073816.png]]
![[Pasted image 20250414074022.png]]
This computer instruction first counts how many requests were created on each specific day using the `evanston311` data. Then, it takes those daily counts and groups them by month. Finally, it calculates the average number of requests that were created per day within each month. The results show that for the first month listed (January 2016), an average of about 23 requests were created each day, and for the second month (February 2016), an average of nearly 31 requests were created each day.

generate series
![[Pasted image 20250415091417.png]]
![[Pasted image 20250415091427.png]]by hours

aggregation with series

![[Pasted image 20250415091755.png]]

![[Pasted image 20250415091850.png]]
using bins
![[Pasted image 20250415091859.png]]
