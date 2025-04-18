**LAG():**

- **Professional Speak:** A window function that provides access to a row at a specified physical offset that precedes the current row within the partition.
- **Simple Speak:** Imagine looking at your spreadsheet of daily sales. `LAG()` lets you see the sales from the _previous_ day on the current day's row. You can look back one row, two rows, or however many you specify.

SQL

```
SELECT
    SaleDate,
    Amount,
    LAG(Amount, 1, 0) OVER (ORDER BY SaleDate) AS PreviousDayAmount
FROM
    Sales;
```

- **Simple Explanation of Example:** For each day's sales, this shows the sales amount from the day before. If it's the very first day, and there's no previous day, it shows 0 (that's what the `0` in the parentheses does).