
# SQL Notes for Beginners

## 📘 What is SQL?
SQL (Structured Query Language) is used to communicate with databases. It's used to store, retrieve, manage, and manipulate data in relational databases like MySQL, PostgreSQL, SQL Server, and Oracle.

---

## 🧱 Basic SQL Concepts

### 1. **Database**
A database is a container that holds tables.

### 2. **Table**
A table is a collection of rows and columns.

---

## 📊 Sample Table: `Employees`

| EmployeeID | FirstName | LastName | Department | Salary |
|------------|-----------|----------|------------|--------|
| 1          | John      | Doe      | HR         | 50000  |
| 2          | Jane      | Smith    | IT         | 60000  |
| 3          | Mike      | Johnson  | IT         | 55000  |
| 4          | Lisa      | Wong     | Finance    | 70000  |
| 5          | Tom       | Brown    | HR         | 52000  |

---

## 🔍 SELECT Queries

### Get all employees:
```sql
SELECT * FROM Employees;
```
**Result:** Returns all rows and columns from the table.

### Get only First and Last Names:
```sql
SELECT FirstName, LastName FROM Employees;
```

### Filter employees from IT department:
```sql
SELECT * FROM Employees
WHERE Department = 'IT';
```

### Employees with salary > 55000:
```sql
SELECT * FROM Employees
WHERE Salary > 55000;
```

---

## 📋 Other Basic Queries

### Sorting Data:
```sql
SELECT * FROM Employees
ORDER BY Salary DESC;
```

### Count of employees:
```sql
SELECT COUNT(*) FROM Employees;
```

### Group by Department:
```sql
SELECT Department, COUNT(*) AS TotalEmployees
FROM Employees
GROUP BY Department;
```

### Average Salary by Department:
```sql
SELECT Department, AVG(Salary) AS AvgSalary
FROM Employees
GROUP BY Department;
```

---

## ✍️ Inserting Data
```sql
INSERT INTO Employees (EmployeeID, FirstName, LastName, Department, Salary)
VALUES (6, 'Emma', 'Stone', 'Marketing', 58000);
```

---

## 📝 Updating Data
```sql
UPDATE Employees
SET Salary = 62000
WHERE FirstName = 'Tom';
```

---

## ❌ Deleting Data
```sql
DELETE FROM Employees
WHERE EmployeeID = 6;
```

---

## ✅ Tips
- SQL is **case-insensitive**.
- Always backup your data before `DELETE` or `UPDATE`.
- Use `WHERE` to avoid updating or deleting the whole table.

---

## 🧠 Practice More
Try to create your own table and run these queries:
```sql
CREATE TABLE Students (
  StudentID INT,
  Name VARCHAR(50),
  Grade INT
);

INSERT INTO Students VALUES (1, 'Alice', 90), (2, 'Bob', 85);
```

Then:
```sql
SELECT * FROM Students;
```
