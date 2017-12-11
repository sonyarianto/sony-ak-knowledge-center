```js
const mysql      = require('mysql');
const connection = mysql.createConnection({
  host     : 'localhost',
  user     : 'root',
  password : 'mypassword',
  database : 'testdb'
});
 
connection.connect();
 
// normal query
connection.query('SELECT * FROM users', function (error, results, fields) {
  if(error) throw error;
  console.log('First username: ' + results[0].username);
});

// query with parameter
connection.query('SELECT * FROM users WHERE username = ?', ['elansuherlan'], function (error, results, fields) {
  if(error) throw error;
  console.log('First username: ' + results[0].username);
});

// query with parameter with variable
var username = 'prasetyama';
connection.query('SELECT * FROM users WHERE username = ?', [username], function (error, results, fields) {
  if(error) throw error;
  console.log('First username: ' + results[0].username);
});

// insert into database
connection.query("INSERT INTO users (username, password) VALUES ('prasetyama', 'keren')", function(error, results, fields) {
  if(error) throw error;
});
 
connection.end();
```
