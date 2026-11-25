# Week 5 Database Assignment: Database Indexing and Optimization

## 📌 Project Overview

This assignment focuses on database indexing, user account management, access control, and SQL security using MySQL.

The practical exercises demonstrate how to manage database indexes, create database users, assign specific privileges, and update user account passwords.

## 🎯 Learning Objectives

By completing this assignment, I gained practical experience in:

1. Managing database indexes using SQL commands.
2. Creating MySQL user accounts with specific host restrictions.
3. Granting database privileges using the `GRANT` statement.
4. Changing user passwords using the `ALTER USER` statement.
5. Understanding database security and access control.

## 🛠️ Technologies Used

- **Database Management System:** MySQL
- **Database Tool:** MySQL Workbench
- **Language:** Structured Query Language (SQL)
- **Project File:** `answers.sql`

## 📂 Project Structure

```text
Week-5-Database/
│
├── answers.sql
└── README.md
```

## 📝 Assignment Questions and Solutions

### Question 1: Drop an Index

**Task:** Write an SQL query to drop an index named `IdxPhone` from the `customers` table.

```sql
DROP INDEX IdxPhone ON customers;
```

**Explanation:**

The `DROP INDEX` statement removes an existing index from a specified table.

**Execution Note:**

The query returned MySQL Error Code 1091 because the index `IdxPhone` did not exist in the `customers` table.

After checking with:

```sql
SHOW INDEX FROM customers;
```

The available indexes were:

- `PRIMARY`
- `SalesRepEmployeeNumber`

Therefore, the requested index could not be dropped.

### Question 2: Create a Database User

**Task:** Create a user named `bob` with a password and restrict access to the `localhost` hostname.

```sql
CREATE USER 'bob'@'localhost'
IDENTIFIED BY '_S$cu3r3!';
```

**Explanation:**

The `CREATE USER` statement creates a new MySQL account.

- Username: `bob`
- Host: `localhost`
- Password: Configured as specified in the assignment.

**Execution Result:** Successfully executed.

### Question 3: Grant INSERT Privilege

**Task:** Grant the `INSERT` privilege to user `bob` on the `salesDB` database.

```sql
GRANT INSERT ON salesDB.* TO 'bob'@'localhost';
```

**Explanation:**

The `GRANT` statement assigns database privileges to a user.

- `INSERT` allows the user to add new records.
- `salesDB.*` applies the privilege to all tables in the `salesDB` database.
- `'bob'@'localhost'` identifies the account receiving the privilege.

**Verification Command:**

```sql
SHOW GRANTS FOR 'bob'@'localhost';
```

### Question 4: Change User Password

**Task:** Change the password for the MySQL user `bob`.

```sql
ALTER USER 'bob'@'localhost'
IDENTIFIED BY '_P$55!23';
```

**Explanation:**

The `ALTER USER` statement modifies an existing MySQL account. In this exercise, it updates the password associated with the `bob` user.

**Execution Note:** Execute the statement using an account with sufficient privileges.

## 🔍 Key SQL Concepts Learned

| SQL Command | Purpose |
|---|---|
| `DROP INDEX` | Removes an existing index |
| `SHOW INDEX` | Displays indexes on a table |
| `CREATE USER` | Creates a MySQL user |
| `GRANT` | Assigns privileges to a user |
| `SHOW GRANTS` | Displays user privileges |
| `ALTER USER` | Modifies an existing user account |

## 🔐 Database Security Practices

This assignment introduced important database security practices:

- Creating individual database accounts instead of sharing administrative accounts.
- Restricting database users to specific connection hosts.
- Applying the principle of least privilege by granting only necessary permissions.
- Using password management commands to maintain account security.
- Verifying user privileges to ensure appropriate access control.

## 📚 Key Takeaways

Through this assignment, I developed practical knowledge of MySQL database administration and security.

I learned how to manage indexes, create user accounts, control database permissions, and update passwords.

I also learned that SQL commands can fail when the specified database object does not exist, making it important to inspect database structures before performing administrative operations.

## 👨‍💻 Author

**Name:** Mohamed Muhumed Rage

**Course:** Database Management

**Week:** 5

**Assignment:** Database Indexing and Optimization

**Institution:** Garissa University

---

*This project was completed as part of the Database module practical assignments.*