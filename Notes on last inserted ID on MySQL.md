When a new AUTO_INCREMENT value has been generated, you can also obtain it by executing a SELECT LAST_INSERT_ID() statement with mysql_query() and retrieving the value from the result set returned by the statement.

When inserting multiple values, the last automatically incremented value is returned.

For LAST_INSERT_ID(), the most recently generated ID is maintained in the server on a per-connection basis. It is not changed by another client. It is not even changed if you update another AUTO_INCREMENT column with a nonmagic value (that is, a value that is not NULL and not 0). Using LAST_INSERT_ID() and AUTO_INCREMENT columns simultaneously from multiple clients is perfectly valid. Each client will receive the last inserted ID for the last statement that client executed.

Taken from http://dev.mysql.com/doc/refman/5.7/en/getting-unique-id.html
