## 1. 
![image](https://github.com/breannly/query-sql/assets/98646323/d29c31bf-4ecd-4d64-a9d2-5a36dfe8c0d0)

Write a SQL query for a report that provides the following information for each person in the Person table, regardless if there is an address for each of those people: FirstName, LastName, City, State.

``` sql
SELECT firstName, lastName, city, state
FROM Persons AS p JOIN Addresses AS a ON p.personId = a.personId
```

## 2.

![image](https://github.com/breannly/query-sql/assets/98646323/af86c605-4a56-44ff-a7b8-838a90d9e62d)

Write a SQL query to get the second highest salary from the Employee table.

``` sql
SELECT COALESCE(MAX(salary), 'NULL') as SecondHighestSalary
FROM Employee
WHERE salary < (SELECT MAX(salary) FROM Employee)
```

## 3.
![image](https://github.com/breannly/query-sql/assets/98646323/34b3472a-1d14-48bb-9cf0-f765cb9e2479)

The Employee table holds all employees including their managers. Every employee has an Id, and there is also a column for the manager Id.
Given the Employee table, write a SQL query that finds out employees who earn more than their managers. For the above table, Joe is the only employee who earns more than his manager.

``` sql
SELECT e1.name
FROM Employee as e1
JOIN Employee AS e2 ON e1.managerid = e2.employeeId
WHERE e1.salary > e2.salary
```

## 4.
![image](https://github.com/breannly/query-sql/assets/98646323/e10132ec-f89d-4d61-bdab-e2a96f31afea)

Write a SQL query to find all duplicate emails in a table named Person.

``` sql
SELECT email
FROM Person
GROUP BY email
HAVING COUNT(*) > 1
```
## 5.
![image](https://github.com/breannly/query-sql/assets/98646323/19df29aa-c60e-4e05-b015-0b41d39cec6b)

Suppose that a website contains two tables, the Customers table and the Orders table. Write a SQL query to find all customers who never order anything.

``` sql
SELECT c.name
FROM Customers AS c
WHERE c.customerId NOT IN (select customerId from Orders)
```

## 6.
![image](https://github.com/breannly/query-sql/assets/98646323/0a924c43-0b92-42fb-ad80-bef847e30efb)

There is a table courses with columns: student and class
Please list out all classes which have more than or equal to 5 students.

``` sql
SELECT c.class
FROM courses AS c
GROUP BY c.class
HAVING COUNT(c.class) >= 5
```
