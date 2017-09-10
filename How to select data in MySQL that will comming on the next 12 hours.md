Example 1:
```sql
SELECT * FROM your_table 
WHERE booking_datetime
BETWEEN UTC_TIMESTAMP() 
AND UTC_TIMESTAMP() + INTERVAL 12 HOUR;
```

Example 2:
```sql
SELECT * FROM your_table 
WHERE booking_datetime
BETWEEN NOW() 
AND NOW() + INTERVAL 12 HOUR;
```                           
