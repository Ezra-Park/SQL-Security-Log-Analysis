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

**SQL Query:**

AND  
![image](https://github.com/user-attachments/assets/df700e17-1674-497a-b7ea-8184e0f3e426)  
When we want to filter results that match two conditions, the 'AND' operator allows us to string together more than one condition, such as a department filter and an office filter.

### 5. Retrieve Employees from Specific Departments (Inclusion)

**Scenario:** Our team needs to perform a targeted security update for employees in either the Finance or Sales departments.

**Objective:** Locate information on all employees whose department is either 'Finance' or 'Sales' from the employees table.

**SQL Query:**

OR  
![image](https://github.com/user-attachments/assets/7e42d8f1-ef97-4b60-9952-a5c4d12e24f2)

### 6. Retrieve All Employees NOT in a Specific Department (Exclusion)

**Scenario:** A specific security update has already been applied to employee computers in the IT department. We now need to gather information on all other employees to schedule their updates.

**Objective:** Exclude employees from the 'Information Technology' department from the employees table. This can be achieved using various exclusion operators.

**SQL Query:**

<>  
![image](https://github.com/user-attachments/assets/58b93a5d-bd0c-4f23-8bed-3cf444b5055a)

!=  
![image](https://github.com/user-attachments/assets/65ee8220-cc57-4d67-9456-d16bbd04a9c7)

NOT  
![image](https://github.com/user-attachments/assets/a9734ddd-e56b-47e0-bb50-ecdc6d56fa7a)

## 💡 Summary

In these examples, we've navigated through simulated databases to return desired information based on specific conditions relevant to cybersecurity investigations. The effective use of SQL operators (e.g., AND, OR, BETWEEN, LIKE, NOT) and a foundational understanding of basic SQL query components (SELECT, FROM, WHERE) are critical tools. These skills enable cybersecurity professionals to discern relevant information quickly and thoroughly, supporting threat detection, incident response, and security posture management.

## 🤝 Connect

Feel free to connect with me on [LinkedIn](https://www.linkedin.com/in/ezra-park-779325330/) if you have any questions or feedback.
