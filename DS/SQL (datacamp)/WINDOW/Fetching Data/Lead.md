**LEAD():**

- **Professional Speak:** A window function that provides access to a row at a specified physical offset that follows the current row within the partition.
- **Simple Speak:** Similar to `LAG()`, but instead of looking backward, `LEAD()` lets you see the sales from the _next_ day on the current day's row. You can look ahead one row, two rows, or however many you specify.

SQL

```
SELECT
    SaleDate,
    Amount,
    LEAD(Amount, 1, 0) OVER (ORDER BY SaleDate) AS NextDayAmount
FROM
    Sales;
```

- **Simple Explanation of Example:** For each day's sales, this shows the sales amount from the next day. If it's the very last day, and there's no next day, it shows 0.