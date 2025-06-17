# SQL Security Log Analysis: Applying Filters to Queries

## 🎯 Project Overview

This project demonstrates the application of Structured Query Language (SQL) for investigating potential security issues by efficiently retrieving relevant information from large datasets. SQL is a critical skill for cybersecurity professionals, enabling quick and thorough analysis of logs and other structured data to identify anomalies, track suspicious activity, and support incident response efforts.

## ☁️ Scenario & Objective

The primary objective is to showcase how various SQL operators and clauses can be used to filter and extract specific records from simulated security-related databases, mirroring tasks performed in a Security Operations Center (SOC) or IT security role. We'll explore common filtering needs across different tables like `log_in_attempts` and `employees`.

## 🧠 Query Examples & Demonstrations

### 1. Retrieve After-Hours Failed Login Attempts

**Scenario:** We need to investigate failed login attempts that occurred outside of standard business hours to identify potential unauthorized activity. Specifically, we'll identify all unsuccessful login attempts made after 18:00 (6 PM).

**Objective:** Parse the `log_in_attempts` table to find records where the `time` is greater than `18:00` AND the `success` value is `0` (indicating a failed attempt). MySQL stores Boolean `FALSE` as `0`.

**SQL Query:**

![image](https://github.com/user-attachments/assets/8055052f-f984-47de-b04e-4bf1ac0ae03c)


### 2. Retrieve Login Attempts on Specific Dates

**Scenario:** A suspicious event was reported on '2022-05-09'. We need to retrieve all login attempts that occurred on this specific day and the day immediately preceding it to understand the full context of activity.

**Objective:** Gather login attempt data for '2022-05-09' and '2022-05-08' from the log_in_attempts table. This can be achieved using either the OR operator or the BETWEEN operator in the WHERE clause.

**SQL Query:**

OR  
![image](https://github.com/user-attachments/assets/b68b4c39-06b5-40b1-956a-8debe7df4368)  
OR allows us to search for data that matches either condition mentioned above.

BETWEEN  
![image](https://github.com/user-attachments/assets/efc08d97-cc56-43ad-a088-9a9d3c96e2a9)  
BETWEEN works in this case because it is an inclusive operator, meaning it includes the dates that we are using to filter. 

### 3. Retrieve Login Attempts from Specific Geos (Exclusion)

**Scenario:** Our team is investigating login attempts that did not originate from our primary operating country, Mexico, as these could represent external threats or policy violations.

**Objective:** Filter the log_in_attempts table to exclude all results where the country field starts with 'MEX'. The LIKE operator with the wildcard % helps to filter out variations such as 'MEX' or 'MEXICO'.

**SQL Query:**

![image](https://github.com/user-attachments/assets/c49f2ff8-4f3c-4002-b6ac-1f85a464c6d7)

### 4. Filter Employee Data for Specific Departments and Locations

**Scenario:** We need to identify employees in the Marketing department who are located in any of our 'East' office buildings to coordinate a specific security update. This requires combining multiple conditions.

**Objective:** Retrieve employee information from the employees table, filtering for department = 'Marketing' AND office_location LIKE 'East%'.

Using AND Operator:
The AND operator allows us to string together multiple conditions, ensuring that all specified conditions are met for a result to be returned.

SQL Query:
