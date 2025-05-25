![[Pasted image 20250407210912.png]]
[[UPSKILL/DS/SQL (datacamp)/MANIPULATING DATA/JOINING]]

Coalesce - **COALESCE** in SQL is like saying: "Give me the first value in this list that is _not_ empty (NULL)."

It checks each item in the list from left to right and returns the very first one it finds that has actual data. If all items are empty, it returns empty.

**Think of it as a backup plan:** "Try the first column, if it's empty, try the second, if that's also empty, try the third, and so on."

![[Pasted image 20250407212016.png]]
