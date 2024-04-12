## Introduction to SQL

Before we dive in to learning **SQL**, we need to learn what it is and what is capable of doing.

- What is **SQL** : **SQL** (Structured Query Language) is a programming language used to operate databases; it includes Database Creation Database Deletion, Fetching Data Rows, etc.

## What Can SQL do?

- SQL can execute queries against a database
- SQL can retrieve data from a database
- SQL can insert records in a database
- SQL can update records in a database
- SQL can delete records from a database
- SQL can create new databases
- SQL can create new tables in a database
- SQL can create stored procedures in a database
- SQL can create views in a database
- SQL can set permissions on tables, procedures, and views

## Why is SQL so important

- It allows us access data in the Relational Database Management Systems (**RDBMS**).
- It allows us create and drop database and table.
- It allows access and manipulate databases.
- It allows us set permissions on tables, procedures and views.
- It allows us to create view, stored procedure, functions in a database.

## Using SQL in Your Web Site

To build a web site that shows data from a database, you will need:

- An RDBMS database program (i.e. MS Access, SQL Server, MySQL)
- To use a server-side scripting language, like PHP , ASP, Nodejs etc
- To use SQL to get the data you want
- To use HTML / CSS to style the page

## Lets talk about RDBMS

**RDBMS** stands for Relational Database Management System.

RDBMS is the basis for SQL, and for all modern database systems such as MS SQL Server, IBM DB2, Oracle, MySQL, and Microsoft Access. In other words it means that it serves as the foundation for **SQL**, i.e RDBMS is a structure that supports the database, and SQL is the language used to communicate with that structure.

## MySQL Database

To be able to experiment with the code examples, you should have MySQL installed on your computer.
<br>

You can download a free MySQL database at [https://www.mysql.com/downloads/](https://www.mysql.com/downloads/).

But for Learning purpose I would be using the xampp mySQL database.

Here's a tutorial to help you install and setup xampp if you don't have it on your PC:
<br>
[Installing and setting up xampp](https://www.ionos.com/digitalguide/server/tools/xampp-tutorial-create-your-own-local-test-server/)
<br>

Here's a tutorial to guide you on how to set up and use the xampp database:
<br>
[Setting up xampp database](https://www.javatpoint.com/creating-mysql-database-with-xampp)

Since I would be using Nodejs to connect and query the database, her's how to do it if you can't :
<br>

- In your terminal type in the following command to install mysql module from npm :

```
npm install mysql
```

- Now you have downloaded and installed a mysql database driver.

Node.js can use this module to manipulate the MySQL database
type this in your index.js (or any name of file of your choice) file:

```javascript
var mysql = require("mysql");
```

- Create Connection
  Start by creating a connection to the database.

Use the username and password from your MySQL database.

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
});
```

- Save the code above in a file called "index.js" and run the file:
