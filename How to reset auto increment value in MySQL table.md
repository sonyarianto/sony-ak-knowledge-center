```sql
ALTER TABLE tablename AUTO_INCREMENT = 1
```

Note that you cannot reset the counter to a value less than or equal to any that have already been used. For MyISAM, if the value is less than or equal to the maximum value currently in the AUTO_INCREMENT column, the value is reset to the current maximum plus one. For InnoDB, if the value is less than the current maximum value in the column, no error occurs and the current sequence value is not changed.
