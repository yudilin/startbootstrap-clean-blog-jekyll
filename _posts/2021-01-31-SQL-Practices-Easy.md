---
layout: post
title: SQL Practice 1 - Easy
subtitle: Questions and solution to some popular SQL questions
background: '/img/posts/sql_practice_join.jpg'
tags:
    - SQL

---

## Third to last employee(s) joinning the company
Here is a snapshot of table employee:
<p align='center'>
<img src="/img/posts/sql/newcoder_sql_2.jpg" align="center" border="0" alt="Here is a snapshot of table employee" width="100%" />
<i>employee table</i>
</p>

```SQL
CREATE TABLE employees (
emp_no int(11) NOT NULL,
birth_date date NOT NULL,
first_name varchar(14) NOT NULL,
last_name varchar(16) NOT NULL,
gender char(1) NOT NULL,
hire_date date NOT NULL,
PRIMARY KEY (emp_no));
```

It's easy to find info about all employees sorted by their hiring date in descent order. Then I apply the limit clause here. 
```SQL
SELECT * FROM employees
ORDER BY hire_date DESC LIMIT 1 OFFSET 2;
```

Giving the question a second thought, it's possible to have muliple employees join the company on the same date, which is the third to last most recent hiring date. In the following code, I select all employees info at the third to last hiring date.
```SQL
SELECT * FROM employees 
WHERE hire_date = 
    (SELECT DISTINCT hire_date FROM employees 
    ORDER BY hire_date DESC LIMIT 1 OFFSET 2);
```

## All employees that have an assigned department
Snapshots of the tables:
<p align='center'>
<img src="/img/posts/sql/newcoder_sql_2.jpg" align="center" border="0" alt="Here is a snapshot of table employee" width="100%" />
<i>employee table</i>
</p>

<p align='center'>
<img src="/img/posts/sql/newcoder_sql_4.jpg" align="center" border="0" alt="Here is a snapshot of table dept_emp" width="100%" />
<i>dept_emp table</i>
</p>

```sql
CREATE TABLE `employees` (
`emp_no` int(11) NOT NULL,
`birth_date` date NOT NULL,
`first_name` varchar(14) NOT NULL,
`last_name` varchar(16) NOT NULL,
`gender` char(1) NOT NULL,
`hire_date` date NOT NULL,
PRIMARY KEY (`emp_no`));

CREATE TABLE `dept_emp` (
`emp_no` int(11) NOT NULL,
`dept_no` char(4) NOT NULL,
`from_date` date NOT NULL,
`to_date` date NOT NULL,
PRIMARY KEY (`emp_no`,`dept_no`));
```
This question asks for employees whose dept_no is not null. I add a where clause to filter the results.
```sql
SELECT e.last_name, e.first_name, d.dept_no
FROM dept_emp d JOIN employees e ON (d.emp_no = e.emp_no)
WHERE d.dept_no is not null;
```
## Second highest salary
Snapshot of the salaies table:
<p align='center'>
<img src="/img/posts/sql/newcoder_sql_7.jpg" align="center" border="0" alt="Here is a snapshot of table salaries" width="100%" />
<i>salaries table</i>
</p>

```sql
CREATE TABLE `salaries` (
`emp_no` int(11) NOT NULL,
`salary` int(11) NOT NULL,
`from_date` date NOT NULL,
`to_date` date NOT NULL,
PRIMARY KEY (`emp_no`,`from_date`));
```
The key constrain in the question is finding the second highest salary which can selected by using limit and offset clause.

### Using group by clause
``` sql
SELECT emp_no, salary
FROM salaries
WHERE to_date = '9999-01-01' AND salary = (
    SELECT salary 
    FROM salaries
    GROUP BY salary
    ORDER BY salary DESC
    LIMIT 1 OFFSET 1
);
```

### Using distinct 
``` sql
SELECT emp_no, salary
FROM salaries
WHERE to_date = '9999-01-01' AND salary = (
    SELECT distinct salary 
    FROM salaries
    ORDER BY salary DESC
    LIMIT 1 OFFSET 1
);
```

### Using rank function
This question can be solved with rank function as well. Note that if there are more than 1 employee receives the second to the highest salary, using rank function will outout all employees.
```sql
SELECT emp_no, salary
FROM (
    SELECT emp_no, salary, rank() OVER (ORDER BY salary DESC) as t
    FROM salaries
    WHERE to_date = '9999-01-01'
)
WHERE t=2;
```

## Remove duplicate records and keep records with the smallest ID
```sql
CREATE TABLE IF NOT EXISTS titles_test (
id int(11) not null primary key,
emp_no int(11) NOT NULL,
title varchar(50) NOT NULL,
from_date date NOT NULL,
to_date date DEFAULT NULL);

insert into titles_test values 
('1', '10001', 'Senior Engineer', '1986-06-26', '9999-01-01'),
('2', '10002', 'Staff', '1996-08-03', '9999-01-01'),
('3', '10003', 'Senior Engineer', '1995-12-03', '9999-01-01'),
('4', '10004', 'Senior Engineer', '1995-12-03', '9999-01-01'),
('5', '10001', 'Senior Engineer', '1986-06-26', '9999-01-01'),
('6', '10002', 'Staff', '1996-08-03', '9999-01-01'),
('7', '10003', 'Senior Engineer', '1995-12-03', '9999-01-01');
```
In mysql, delete can't be processed with the same select querry. Thus, I assign a name for the subquery result.
```sql
delete from titles_test where id not in (
    select * from (
        select min(id) from titles_test group by emp_no
    ) l  
);
```
