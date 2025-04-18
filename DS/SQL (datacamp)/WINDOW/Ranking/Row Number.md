**ROW_NUMBER():**

- **Professional Speak:** A window function that assigns a unique sequential integer to each row within a partition, according to the specified ordering.
- **Simple Speak:** This just gives each row a simple number, like numbering the lines in your spreadsheet. It doesn't care about ties; it just goes 1, 2, 3, 4, and so on, based on how you've ordered the data.

SQL

```
SELECT
    Athlete,
    Medals,
    ROW_NUMBER() OVER (ORDER BY Athlete ASC) AS AthleteNumber
FROM
    Summer_Medals
WHERE
    Year = 2012
ORDER BY
    Athlete ASC;
```

- **Simple Explanation of Example:** This assigns a unique number to each athlete in the 2012 Summer Olympics, ordered alphabetically by their name. Even if two athletes have the same number of medals, they will get different row numbers.