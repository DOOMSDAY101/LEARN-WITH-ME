# SQL CREATE DATABASE Statement

In this section we are going to be learning about SQL tables and how to create them.

#### what is a table?<br>

In RDBMS, Database tables are used to store the data in the form of some structures(Rows and Columns)
<br>

**_Columns (fields):_** Columns are vertical elements in a table. Each columns in a table holds specific attribute information, and column properties such as column name and data types (Integer,Char,String).
<br>

**_Rows (records):_** Rows are horizontal elements in a table and users can add data or retrieve data by executing queries. A row contains the actual data we are storing.

## Creating a Table

To create a table in MySQL, use the "CREATE TABLE" statement.

**_Make sure you define the name of the database when you create the connection_**

**_Syntax:_**

```sql
CREATE TABLE table_name (
column1 datatype,
column2 datatype,
column3 datatype,
....
);
```

Complete code:

```js
var mysql = require("mysql");

var con = mysql.createConnection({
  host: "localhost",
  user: "yourusername",
  password: "yourpassword",
  database: "mydb",
});

con.connect(function (err) {
  if (err) throw err;
  console.log("Connected!");

  //SQL QUERY
  var sql = `CREATE TABLE Persons   
    PersonID int,
    LastName varchar(255),
    FirstName varchar(255),
    Address varchar(255),
    City varchar(255)`;

  con.query(sql, function (err, result) {
    if (err) throw err;
    console.log("Table created");
  });
});
```

Here we created a table Persons using the CREATE TABLE Syntax in SQL.
<br>

PersonID is a **Column** of type int that will hold an integer.

The LastName, FirstName, Address, and City **Columns** are of type varchar and will hold characters, and the maximum length for these fields is 255 characters.

Save the code above in a file called "sql-create-table.js" and run the file:

```
node demo_create_table.js
```

And yay🎉🎉 we just created our Table using Using SQL.
