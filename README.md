# query-sql
## 1. 
![image](https://github.com/breannly/query-sql/assets/98646323/d29c31bf-4ecd-4d64-a9d2-5a36dfe8c0d0)

Write a SQL query for a report that provides the following information for each person in the Person table, regardless if there is an address for each of those people: FirstName, LastName, City, State

``` sql
SELECT firstname, lastname, city, state
FROM Persons AS p JOIN Addresses AS a ON p.personId = a.personId
```
