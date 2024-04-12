# SQL CREATE DATABASE Statement

#### what is a database?

A database is a structured collection of data that is stored in a computer system.<br>
SQL database server stores data into [Tables](4-sql-create-table.md). tables are database objects used to collect data in **Row** (record) and **Column** (field) format.

The CREATE DATABASE statement is used to create a new SQL database.

**_Syntax_**

```sql
CREATE DATABASE databasename;
```

CREATE DATABASE Example
The following SQL statement creates a database called "testDB":

**_Example_**

```sql
CREATE DATABASE testDB;
```

Complete code:

```javascript
var mysql = require("mysql");

var con = mysql.createConnection({
  host: "localhost",
  user: "yourusername",
  password: "yourpassword",
});

con.connect(function (err) {
  if (err) throw err;
  console.log("Connected!");

  con.query("CREATE DATABASE testDB", function (err, result) {
    if (err) throw err;
    console.log("Database created");
  });
});
```

Save the code above in a file called "sql_create-db.js" and run the file:

```
node demo_create_db.js
```

And yay🎉🎉 we just created our database.
