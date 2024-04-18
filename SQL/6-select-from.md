# SQL SELECT FROM Statement

In this section we are going to be learning about SQL **SELECT FROM** statement and how to use them.

#### what is SQL SELECT FROM Statement?<br>

The SQL **SELECT** statement is used to fetch data from a database table.

**_Syntax:_**

```sql
SELECT column1, column2, ...
FROM table_name;
```

Complete code:

```js
var mysql = require("mysql");

var con = mysql.createConnection({
  host: "localhost",
  user: "yourusername",
  password: "yourpassword",
  database: "testDB",
});

con.connect(function (err) {
  if (err) throw err;
  con.query("SELECT * FROM Persons", function (err, result, fields) {
    if (err) throw err;
    console.log(result);
  });
});
```

Th above code selects all the columns in the table.

Save the code above in a file called "sql-select-from.js" and run the file:

```
node sql-select-from.js
```

## Selecting Columns

To select only some of the columns in a table, use the "SELECT" statement followed by the column name.

Example
To select the LastName and the FirstName columns only:

```js
var mysql = require("mysql");

var con = mysql.createConnection({
  host: "localhost",
  user: "yourusername",
  password: "yourpassword",
  database: "testDB",
});

con.connect(function (err) {
  if (err) throw err;
  con.query("SELECT LastName, FirstName FROM Persons", function (err, result) {
    if (err) throw err;
    console.log(result);
  });
});
```
