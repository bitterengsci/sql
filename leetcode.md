
<!-- TOC -->

- [1. Leetcode 175. Combine Two Tables](#1-leetcode-175-combine-two-tables)
- [2. Leetcode 176. Second Highest Salary](#2-leetcode-176-second-highest-salary)
- [3. Leetcode 177. Nth Highest Salary](#3-leetcode-177-nth-highest-salary)
- [4. Leetcode 178. Rank Scores](#4-leetcode-178-rank-scores)
- [5. Leetcode 180. Consecutive Numbers](#5-leetcode-180-consecutive-numbers)
- [6. Leetcode 181. Employees Earning More Than Their Managers](#6-leetcode-181-employees-earning-more-than-their-managers)
- [7. Leetcode 182. Duplicate Emails](#7-leetcode-182-duplicate-emails)
- [8. Leetcode 183. Customers Who Never Order](#8-leetcode-183-customers-who-never-order)
- [9. Leetcode 184. Department Highest Salary](#9-leetcode-184-department-highest-salary)
- [10. Leetcode 185. Department Top Three Salaries](#10-leetcode-185-department-top-three-salaries)
- [11. Leetcode 196. Delete Duplicate Emails](#11-leetcode-196-delete-duplicate-emails)
- [12. Leetcode 197. Rising Temperature](#12-leetcode-197-rising-temperature)
- [13. Leetcode 262. Trips and Users](#13-leetcode-262-trips-and-users)

<!-- /TOC -->

# Leetcode 175. Combine Two Tables
```sql
SELECT FirstName, LastName, a.City, a.State
FROM Person AS p
LEFT JOIN Address AS a
ON p.PersonId = a.PersonId
```

# Leetcode 176. Second Highest Salary
```sql
-- Approach: Using sub-query and LIMIT clause 
-- Sort the distinct salary in descend order and then utilize the LIMIT clause to get the second highest salary.
SELECT DISTINCT Salary AS SecondHighestSalary
FROM Employee
ORDER BY Salary DESC
LIMIT 1 OFFSET 1

-- Wrong if there is no such second highest salary (i.e. only one record in this table). We can take this as a temp table.
SELECT
    (SELECT DISTINCT Salary
    FROM Employee
    ORDER BY Salary DESC
    LIMIT 1 OFFSET 1) AS SecondHighestSalary

-- Approach: Using IFNULL and LIMIT clause
SELECT
    IFNULL(
      (SELECT DISTINCT Salary
       FROM Employee
       ORDER BY Salary DESC
        LIMIT 1 OFFSET 1),
    NULL) AS SecondHighestSalary
```

# Leetcode 177. Nth Highest Salary

# Leetcode 178. Rank Scores
```sql
-- Approach:
SELECT Score, DENSE_RANK() over (Order by Score DESC) as "Rank"
from Scores

-- Approach:
SELECT s.Score, r.Rank
FROM Scores AS s
LEFT JOIN (SELECT d.Score, ROW_NUMBER() OVER(ORDER BY d.Score desc) AS 'Rank'
           FROM (SELECT distinct Score FROM Scores) AS d) AS r
ON s.Score = r.Score
ORDER BY r.Score desc
```

# Leetcode 180. Consecutive Numbers

# Leetcode 181. Employees Earning More Than Their Managers

# Leetcode 182. Duplicate Emails
```sql
-- Approach: Using GROUP BY and a temporary table
SELECT Email FROM
(SELECT Email, COUNT(Email) AS num
  FROM Person
  GROUP BY Email
) AS statistic
WHERE num > 1

-- Approach: Using GROUP BY and HAVING condition
SELECT Email
FROM Person
GROUP BY Email
HAVING COUNT(Email) > 1

-- Approach: JOIN
SELECT DISTINCT p1.Email
FROM Person p1, Person p2
WHERE p1.Email = p2.Email and p1.id != p2.id
```

# Leetcode 183. Customers Who Never Order

# Leetcode 184. Department Highest Salary
```sql
-- Approach: Using JOIN and IN clause
SELECT
    Department.name AS 'Department',
    Employee.name AS 'Employee',
    Salary
FROM Employee
JOIN Department ON Employee.DepartmentId = Department.Id
WHERE (Employee.DepartmentId , Salary) IN
      (SELECT DepartmentId, MAX(Salary)
        FROM Employee
        GROUP BY DepartmentId
	   )
```

# Leetcode 185. Department Top Three Salaries

# Leetcode 196. Delete Duplicate Emails

# Leetcode 197. Rising Temperature
```sql
-- Approach:
SELECT w1.Id
FROM Weather w1, Weather w2
where DATEDIFF(w1.RecordDate, w2.RecordDate) = 1 and (w1.Temperature > w2.Temperature)

-- Approach: Using JOIN and DATEDIFF() clause
SELECT weather.Id
FROM weather
JOIN weather w 
    ON DATEDIFF(weather.RecordDate, w.RecordDate) = 1
    AND weather.Temperature > w.Temperature
```

# Leetcode 262. Trips and Users