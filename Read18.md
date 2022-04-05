# SQL Injection  

What is SQL injection (SQLi)?
SQL injection is a web security vulnerability that allows an attacker to interfere with the queries that an application makes to its database. It generally allows an attacker to view data that they are not normally able to retrieve. This might include data belonging to other users, or any other data that the application itself is able to access. In many cases, an attacker can modify or delete this data, causing persistent changes to the application's content or behavior.  
   
#### SQL in Web Pages
SQL injection usually occurs when you ask a user for input, like their username/userid, and instead of a name/id, the user gives you an SQL statement that you will unknowingly run on your database.  

```
txtUserId = getRequestString("UserId");
txtSQL = "SELECT * FROM Users WHERE UserId = " + txtUserId;
```  
#### SQL injection examples  

- Retrieving hidden data  
- Subverting application logic  
- UNION attacks  
- Examining the database  
- Blind SQL injection  

# Many-to-many relationships  
  
A many-to-many relationship occurs when multiple records in a table are associated with multiple records in another table. For example, a many-to-many relationship exists between customers and products: customers can purchase various products, and products can be purchased by many customers.  

![Many-to-many](assets01/read18.png)
