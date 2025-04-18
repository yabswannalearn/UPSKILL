so pivoting ay pag rotate ng table, yung rows magiging column

![[Pasted image 20250418142953.png]]

CROSSTAB
![[Pasted image 20250418143035.png]]
![[Pasted image 20250418143042.png]]
Example code:
`
```
-- Create the correct extension to enable CROSSTAB

CREATE EXTENSION IF NOT EXISTS tablefunc;

  

SELECT * FROM CROSSTAB($$

  SELECT

    Gender, Year, Country

  FROM Summer_Medals

  WHERE

    Year IN (2008, 2012)

    AND Medal = 'Gold'

    AND Event = 'Pole Vault'

  ORDER By Gender ASC, Year ASC;

-- Fill in the correct column names for the pivoted table

$$) AS ct (gender VARCHAR,

           "2008" VARCHAR,

           "2012" VARCHAR)

  

ORDER BY Gender ASC;
```
``
![[Pasted image 20250418144040.png]]

so ginawa dito ay pinalitan mo yung output kung saan magiging column yung years and country


