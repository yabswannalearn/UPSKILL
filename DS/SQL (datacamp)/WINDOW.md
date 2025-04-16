[[WINDOW FUNCTIONS]]


- **`PARTITION BY`**: Ito ay ginagamit para hatiin ang mga row (linya ng data) mo sa mas maliliit na grupo. Isipin mo na parang hinahati mo ang mga estudyante base sa kanilang section.
- **`RANK()`**: Nagbibigay ito ng "rank" o posisyon sa bawat row sa loob ng isang grupo. Kung may magkapareho ng value (halimbawa, parehong grado), pareho din ang rank nila, pero lalaktawan ang susunod na rank number (e.g., 1, 2, 2, 4).
- **`RANK() OVER (PARTITION BY ...)`**: Pinagsasama nito ang dalawa. Nagra-rank ka (`RANK()`) sa bawat row, pero ang pagra-rank na ito ay _inuulit_ para sa bawat grupo na ginawa ng `PARTITION BY`.

**Real-life Example:**

Isipin mo may listahan ka ng mga `Sales Agent`, `Branch` kung saan sila naka-assign, at `Total Sales` nila. Gusto mong malaman ang rank ng bawat ahente base sa kanilang benta, pero _sa loob lang ng kanilang branch_.

Gagamitin mo ang:

SQL

```
SELECT
  AgentName,
  Branch,
  TotalSales,
  RANK() OVER (PARTITION BY Branch ORDER BY TotalSales DESC) AS RankInBranch
FROM SalesData;

```

- **`PARTITION BY Branch`**: Hahatiin nito ang data kada branch (e.g., lahat ng taga-Manila Branch magkakasama, lahat ng taga-Cebu Branch magkakasama).
- **`ORDER BY TotalSales DESC`**: Pagsusunud-sunurin nito ang mga ahente sa loob ng bawat branch base sa pinakamataas na benta (DESCending).
- **`RANK()`**: Magbibigay ito ng Rank 1 sa top agent ng Manila, Rank 1 sa top agent ng Cebu, at iba pa. Kung may magkaparehong sales sa isang branch, pareho sila ng rank.


OVER CLAUSE
![[Pasted image 20250405081817.png]]

RANK FUNCTION

![[Pasted image 20250405081847.png]]

![[Pasted image 20250405081951.png]]

PARTITION BY
![[Pasted image 20250406000704.png]]

![[Pasted image 20250406000715.png]]

sliding window
![[Pasted image 20250406001407.png]]


![[Pasted image 20250406001150.png]]

![[Pasted image 20250406001211.png]]

![[Pasted image 20250417063403.png]]

![[Pasted image 20250417063759.png]]
[[ORDER BY keyword]]
![[Pasted image 20250417063808.png]]
order by with window functions

![[Pasted image 20250417064336.png]]
lag, makikita mo to sa [[DATE TIME]] 

partition by with window

![[Pasted image 20250417065034.png]]
![[Pasted image 20250417065104.png]]