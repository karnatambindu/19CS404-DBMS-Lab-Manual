Experiment 4: Aggregate Functions, Group By and Having Clause
AIM
To study and implement aggregate functions, GROUP BY, and HAVING clause with suitable examples.

THEORY
Aggregate Functions
These perform calculations on a set of values and return a single value.

MIN() – Smallest value
MAX() – Largest value
COUNT() – Number of rows
SUM() – Total of values
AVG() – Average of values
Syntax:

SELECT AGG_FUNC(column_name) FROM table_name WHERE condition;
GROUP BY
Groups records with the same values in specified columns. Syntax:

SELECT column_name, AGG_FUNC(column_name)
FROM table_name
GROUP BY column_name;
HAVING
Filters the grouped records based on aggregate conditions. Syntax:

SELECT column_name, AGG_FUNC(column_name)
FROM table_name
GROUP BY column_name
HAVING condition;
Question 1
-- How many appointments are scheduled for each patient?

-- SELECT PatientID , count(AppointmentID) as TotalAppointments
FROM Appointments 
group by PatientID
ORDER BY PatientID
Output:

{59EAFE28-F2FE-4685-87AC-F5C38E131024}

Question 2
-- What is the average duration of insurance coverage for patients covered by each insurance company?

-- SELECT InsuranceCompany, AVG(enddate - startdate) AS AvgCoverageDurationDays
FROM Insurance
GROUP BY InsuranceCompany;
Output:

{5E1B6DCE-82EE-4661-863A-653DC58F0C10}

Question 3
-- How many prescriptions were written in each frequency category (e.g., once daily, twice daily)?

-- select Frequency, count(PatientID) as TotalPrescriptions
FROM Prescriptions
group by Frequency; 
Output:

{7940C970-305A-43E3-BD21-5D858FD0B673}

Question 4
-- Write a SQL query to find the average salary of all employees?

-- SELECT AVG(income) AS Average_Salary 
FROM employee; 
Output:

{6E07E564-49A8-4309-BC0F-C03B21F027FF}

Question 5
-- Write a SQL query that counts the number of unique salespeople. Return number of salespeople.

-- SELECT count(distinct salesman_id) AS COUNT
FROM orders;
Output:

{EBCD0F74-25DF-4E69-BF48-B6A51EE30996}

Question 6
-- Write a SQL query to return the total number of rows in the 'customer' table where the city is not Noida.

-- SELECT COUNT(id) AS COUNT FROM customer 
WHERE city != 'Noida';
Output:

{BE69303F-69BA-4D3B-A162-4492974D9BE1}

Question 7
-- Write a SQL query to find What is the age difference between the youngest and oldest employee in the company.

-- SELECT MAX(age) - MIN(age) AS age_difference 
FROM employee;
Output:

{BBF6CEF3-B9A6-4440-BA68-BC62169CCFC9}

Question 8
-- Write the SQL query that accomplishes the grouping of data by joining date (jdate), calculates the minimum work hours for each date, and excludes dates where the minimum work hour is not less than 10.

-- SELECT jdate, MIN(workhour) 
FROM employee1 
GROUP BY jdate 
HAVING MIN(workhour) < 10; 
Output:

{BEF868D3-8A63-4C6C-80D1-A75877DC0409}

Question 9
-- Write the SQL query that accomplishes the grouping of data by joining date (jdate), calculates the total work hours for each date, and excludes dates where the total work hour sum is not greater than 40.

-- SELECT jdate, SUM(workhour)
FROM employee1 
GROUP BY jdate
HAVING SUM(workhour) >= 40;
Output:

{68F9523B-28F9-4932-919D-415BBC654F1B}

Question 10
-- Write the SQL query that achieves the grouping of data by age, calculates the minimum income for each age group, and includes only those age groups where the minimum income is less than 400,000.

-- SELECT age, MIN(income) 
FROM employee 
GROUP BY age
HAVING MIN(income) < 400000;
Output:

{14AC3AAB-2780-4B83-BE4B-D429A82AC3AB}

RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
