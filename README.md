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

```sql
![image](https://github.com/user-attachments/assets/31dbad1b-8a87-4929-9966-13bb3ecf0fbc)

-- Example SQL query to retrieve after-hours failed login attempts
SELECT *
FROM log_in_attempts
WHERE time > '18:00:00' AND success = 0;
