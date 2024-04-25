# SQL JOIN CLAUSE

In this section we are going to be talking about a quite complex clause used in SQL called **JOIN**. It's confusing to uderstand at first but really easy as you understand it better.

#### What is SQL JOIN Statement?<br>

The **JOIN** clause is used to combine rows from two or more **tables** that have related/similar column between them.

In practical terms: let's say you have two tables in your database, one to store the customer information (name,address,age etc) and the other to store the customer order information (orderid,orderdate etc).

How do you combine and print out the customer name and the orderdate for a particular order based on the userid since they are in different tables... that's where the **JOIN** clause comes in.
The **JOIN** clause can be used to carry out that complex(not so complex) task.

**_Syntax:_**<br>

```sql
SELECT columns
FROM table1
INNER JOIN table2
ON table.column = table2.column
```

**Example:**<br>
For this example we will be using two tables named Orders and Customers that have a matching column of customerID, and we will be selecting the OrderID from the Orders table, CustomerName from the Customers table & OrderDate from the Orders table.

```sql
SELECT Orders.OrderID, Customers.CustomerName, Orders.OrderDate
FROM Orders
INNER JOIN Customers
ON Orders.Orders.CustomerID=Customers.CustomerID;
```

**Explanation:**<br>
Line 1 (SELECT): Selects the columns from the various tables.
Line 2 (FROM): The name of the first table
Line 3 (INNER JOIN): Joins it with the second table
Line 4 (ON): The related columns between them.

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
  con.query(
    `SELECT Orders.OrderID, Customers.CustomerName, Orders.OrderDate
    FROM Orders
    INNER JOIN Customers
    ON Orders.Orders.CustomerID=Customers.CustomerID;`,
    function (err, result, fields) {
      if (err) throw err;
      console.log(result);
    }
  );
});
```

Save the code above in a file called "sql-join.js" and run the file:

```
node sql-join.js
```
