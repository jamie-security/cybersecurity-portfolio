# Security Investigation using SQL Report

## Summary
I completed this project as part of the Google Cybersecurity Professional Certificate course.

This project involved investigating potential security issues concerning login attempts and employee machines at a large organisation. To perform these tasks, I queried the `employees` and `log_in_attempts` tables.

## Investigating Failed After Hours Login Attempts
During my investigation, I found that multiple login attempts were being made after business hours, these all had to be investigated. To do this I used the following SQL code:
```
SELECT *
FROM log_in_attempts
WHERE login_time > '18:00' AND success = 0;
```
By using `SELECT *` and `FROM log_in_attempts`, I retrieved all data inside the table. By using the `WHERE` clause, I was able to filter the resulting data with two conditions.

The first condition, `login_time > '18:00'` filters the data to display only login times that occured after 18:00. 

The second condition, `success = 0;` filters the data to display only login attempts that have failed. In this database, failed attempts are represented as a `0` and successful attempts are represented as a `1`.

The `AND` operator requires that both the conditions need to be met for results to appear. This therefore enabled me to investigate failed login attempts after business hours

## Investigating Login Attempts on Specific Dates
A suspicious event occured on 2022-05-09. I needed to investigate all login attempts that occured on this day or the day before. To do this I used the following SQL code:
```
SELECT *
FROM log_in_attempts
WHERE login_date = '2022-05-09- OR login_date = '2022-05-08';
```
By using the `OR` operator I was able to filter the data where either date condition was true. This allowed me and the security team to compare login activity across the two dates.

## Investigating Login Attempts Outside of Mexico
My investigation led my team and I to believe that the issues regarding login attempts were occuring outside of Mexico. We therefore, needed to filter the login attempts to exclude attempts made in Mexico. To do this I used the following SQL code:
```
SELECT *
FROM log_in_attempts
WHERE NOT country LIKE 'MEX%';
```
I used the `LIKE` operator, paired with the `%` wildcard to search for patterns rather than an exact value. The `%` wildcard represents any number of characters after `MEX`, this allowed me to query for results matching both `MEX` and `MEXICO`.

The `NOT` operator was used to exclude results where `country` was `MEX` or `MEXICO`, leaving login attempts originiating outside of Mexico to be displayed. 

## Identifying Marketing Employees in the East Building
Another task I had to complete was identifying employee machines that needed to be updated. I had to update the machines for employees that were in the marketing department and were in the east building. To do this I used the following SQL code:
```
SELECT *
FROM employees
WHERE department = 'Marketing' and office LIKE 'East%';
```
I included two conditions, first one being `department = 'Marketing'`. This filtered the data to display employees in the marketing department only.

The second condition, `office LIKE 'East%'`, filtered the data to display eployees with offices beginning with `East`.

I used the `AND` operator to ensure that the results displayed met both conditions. This meant that only employees in the marketing department in the east building were displayed. 

## Identifying Employees in Finance or Sales
After updating the machines for marketing employees in the east building, I then had to update the machines for employees in either the finance or sales depatments. To do this I used the following SQL code:

```
SELECT *
FROM employees
WHERE department = 'Finance' OR department = 'Sales';
```

By using the `OR` operator, results were displayed where either condition was true. This therefore displayed employees part of the finance or sales departments. 

## Identifying Employees Outside of IT Department
My final query was used to identify employees who aren't part of the IT department. To do this I used:
```
SELECT *
FROM employees
WHERE NOT department = 'Information Technology';
```
The `NOT` operator displayed results of employees in any department that wasn't IT. This allowed me to push through final updates for machines needing them.

## Security Relevance
SQL is used by security professionals when they're investigating large amounts of data. By using SQL in this project I have been able to:
- Identify and investigate suspicious login activity outside of business hours
- Compare login activity across specific dates
- Identify login attempts originating outside a specific country
- Filter employees based on their departments and office location to push security updates to machines

## Reflection
This project has helped me improve my understanding of SQL and how it is used as part of investigations. I've learnt how SQL operators such as `AND`, `OR` and `NOT` are used with conditions to find relevant data from databases. Finally, I've been able to learn how `LIKE` and wildcards such as `%` are used to search for patterns in data. 

