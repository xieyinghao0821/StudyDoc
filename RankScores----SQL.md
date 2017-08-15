```
SELECT s1.Score,COUNT(*)
FROM scores s1
INNER JOIN (SELECT DISTINCT Score FROM scores) s2
ON s1.Score <= s2.Score
GROUP BY s1.Id
ORDER BY s1.Score DESC 
```
```
SELECT Score,(SELECT count(*) FROM (SELECT distinct Score s FROM Scores) tmp WHERE s >= Score) Rank
FROM Scores
ORDER BY Score desc
```
这里tmp不可少，否则会报Every derived table must have its own alias错误。
