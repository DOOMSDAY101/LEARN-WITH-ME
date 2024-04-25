# SQL UPDATE Keyword

The SQL **UPDATE** keyword is used to update(alter/edit) existing records in a table.

**_Syntax:_**

```sql
UPDATE table_name
SET column = 'value'
WHERE column = 'value'
```

Complete code:
Example: To set the FirstName of a user with id 1 to "Adekunle":

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
    "UPDATE Persons SET FirstName = 'Adekunle' WHERE id = 1",
    function (err, result) {
      if (err) throw err;
      console.log(result);
    }
  );
});
```

**NOTE:** Always use the **WHERE** Statement when using this keyword else all the records would be updated.

Save the code above in a file called "sql-update.js" and run the file:

```
node sql-select-from.js
```
