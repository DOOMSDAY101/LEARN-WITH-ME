# SQL INSERT INTO Statement

In this section we are going to be learning about SQL **INSERT INTO** statement and how to use them.

#### what is SQL INSERT INTO Statement?<br>

So now we have created our database and our Table, How do we input data into data into this table we just created... This is where the SQL **INSERT STATEMENT** comes in.

The SQL INSERT INTO is an SQL query used to input data our data int the table we've created.<br>
It is used to add new rows of data into a table in the database.
<br>
<br>
**NOTE:**<br>

- Each value in the records we are inserting in a table must be of the same datatype as the respective column.
- The data value being passed must satisfy the constraints of the column.
- The values passed in the records we are inserting in a table using this statement should match the number of columns in the table.

**_Syntax:_**

```sql
INSERT INTO table_name (column1, column2, column3, ...)
VALUES (value1, value2, value3, ...);
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
  console.log("Connected!");

  //SQL INSERT STATEMENT
  var sql = `INSERT INTO Persons 
    (LastName,FirstName,Address,City) 
    VALUES ('Sulaiman','Ifeoluwa','Surulere, Lagos Nigeria','Lagos')
    `;
  con.query(sql, function (err, result) {
    if (err) throw err;
    console.log("1 record inserted");
  });
});
```

Save the code above in a file called "sql-insert-into.js" and run the file:

```
node sql-insert-into.js
```

And yay🎉🎉 we just inserted our first data.

## Insert Multiple Records

In the last example we learnt how to insert only a single record. To insert more than one record, make an array containing the values, and insert a question mark in the sql, which will be replaced by the value array:
INSERT INTO customers (name, address) VALUES ?

EXAMPLE

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
  console.log("Connected!");

  //SQL INSERT STATEMENT
  var sql = `INSERT INTO Persons 
    (LastName,FirstName,Address,City) 
    VALUES (?)
    `;
  var values = [
    ["Peter", "Parker", "Highway 71", "Kentucky"],
    ["Adekunle", "Adewale", "Ibadan Nigeria", "Ibadan"],
  ];
  con.query(sql, [values], function (err, result) {
    if (err) throw err;
    console.log("1 record inserted");
  });
});
```
