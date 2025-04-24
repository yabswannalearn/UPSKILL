**ROLLUP:**

- **Professional Speak:** A clause used with the `GROUP BY` statement to generate subtotals along a hierarchy of grouping columns. It creates aggregate results at different levels of aggregation, moving from the most detailed to a grand total.
- **Simple Speak:** Imagine you're summarizing sales by City and then by Region. `ROLLUP` gives you the total sales for each City, and then it _also_ gives you the total sales for each Region (by adding up all the cities in that region), and finally, the grand total sales for everyone. It moves up levels of detail.

SQL

```
SELECT
    Region,
    City,
    SUM(SalesAmount) AS TotalSales
FROM
    Sales
GROUP BY ROLLUP (Region, City);
```

- **Simple Explanation of Example:** This will show:
    - Total sales for each City within each Region.
    - Total sales for each Region (summing up all its cities).
    - The overall total sales.

![[Pasted image 20250418150613.png]]
![[Pasted image 20250418150708.png]]
![[Pasted image 20250418150720.png]]

---
