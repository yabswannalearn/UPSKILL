**DENSE_RANK():**

- **Professional Speak:** A window function that assigns a unique rank to each distinct row within a partition, based on the specified ordering. Ranks are consecutive, with no gaps even if there are ties.
- **Simple Speak:** Imagine you're ranking people based on their score. `DENSE_RANK()` gives the top scorer rank 1. If two people have the same top score, they both get rank 1, and the next unique score gets rank 2 (no skipped numbers).

SQL

```
SELECT
    Athlete,
    Medals,
    DENSE_RANK() OVER (ORDER BY Medals DESC) AS RankByMedals
FROM
    Summer_Medals
WHERE
    Year = 2012
ORDER BY
    Medals DESC;
```

- **Simple Explanation of Example:** This ranks athletes by the number of medals they won in 2012. If multiple athletes have the same number of medals, they get the same rank, and the next rank will be the immediate next whole number.