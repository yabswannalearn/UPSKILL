**PARTITION BY:**

- **Professional Speak:** A clause used within window functions to divide the rows of a query result set into partitions. The window function is then applied to each partition independently.
- **Simple Speak:** Imagine you're sorting your spreadsheet into separate groups based on a certain column (like "City"). `PARTITION BY` does this grouping _before_ doing a special calculation within each group. It's like saying, "Do this calculation separately for each city."

SQL

```
SELECT
    ProductName,
    Category,
    Price,
    AVG(Price) OVER (PARTITION BY Category) AS AverageCategoryPrice
FROM
    Products;
```

- **Simple Explanation of Example:** This example finds the average price of products _within each category_. It groups all the "Electronics" together to calculate their average, then groups all the "Books" together to calculate their average, and so on.