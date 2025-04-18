- **Professional Speak:** A clause used with the `GROUP BY` statement to generate subtotals for all possible combinations of the specified grouping columns. It provides aggregate results for every level of the grouping hierarchy and also for all cross-combinations.
- **Simple Speak:** Similar to `ROLLUP`, but it's more thorough. If you're summarizing sales by City and Region, `CUBE` will give you:
    - Total sales for each City within each Region.
    - Total sales for each Region (summing up all its cities).
    - Total sales for each City (across all regions).
    - The overall grand total sales. It gives you totals for _every possible grouping_.

SQL

```
SELECT
    Region,
    City,
    SUM(SalesAmount) AS TotalSales
FROM
    Sales
GROUP BY CUBE (Region, City);
```

- **Simple Explanation of Example:** This will show all the results from the `ROLLUP` example, _plus_ the total sales for each City regardless of the Region.

non hierarchial [[Roll up]]

![[Pasted image 20250418150802.png]]

![[Pasted image 20250418150808.png]]![[Pasted image 20250418150814.png]]