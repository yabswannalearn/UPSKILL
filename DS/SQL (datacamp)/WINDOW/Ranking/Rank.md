**RANK():**

- **Professional Speak:** A window function that assigns a unique rank to each row within a partition, based on the specified ordering. Ranks may have gaps when there are ties.
- **Simple Speak:** Similar to `DENSE_RANK()`, it ranks people by score. The top scorer gets rank 1. If two people tie for the top score, they both get rank 1, but the next unique score will get rank 3 (skipping rank 2 because of the tie).

SQL

```
SELECT
    Athlete,
    Medals,
    RANK() OVER (ORDER BY Medals DESC) AS RankByMedals
FROM
    Summer_Medals
WHERE
    Year = 2012
ORDER BY
    Medals DESC;
```

- **Simple Explanation of Example:** This also ranks athletes by medals in 2012. If there's a tie in medals, the next rank will be skipped.