* http://mysql.rjweb.org/doc.php/partitionmaint
* https://dev.mysql.com/doc/refman/5.7/en/partitioning-management-range-list.html
* https://dev.mysql.com/doc/refman/5.7/en/alter-table-partition-operations.html

Notes:

It is very important to remember that, when you drop a partition, you also delete all the data that was stored in that partition. If you intend to change the partitioning of a table without losing data, use `ALTER TABLE ... REORGANIZE PARTITION` instead.
