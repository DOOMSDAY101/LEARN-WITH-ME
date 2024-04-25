# SQL WHERE CLAUSE

The **WHERE** clause is used to filter records.

It is used to extract only those records that fulfill a specified condition.

**_Syntax:_**

```sql
SELECT column1, column2, ...
FROM table_name
WHERE condition;
```

**NOTE:**
The WHERE clause is not only used in SELECT statements, it is also used in UPDATE, DELETE, etc.!

**Example:**
<br>
To select only a user with the id of 10

```sql
SELECT * FROM Persons
WHERE id = 1
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
  con.query("SELECT * FROM Persons WHERE id = 1", function (err, result) {
    if (err) throw err;
    console.log(result);
  });
});
```
