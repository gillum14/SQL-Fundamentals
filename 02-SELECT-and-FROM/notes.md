# SELECT and FROM

## Overview

The `SELECT` and `FROM` statements are the foundation of SQL. They are used to retrieve information from a database by specifying which columns to return and which table to retrieve them from.

As a cybersecurity analyst, SQL is commonly used to investigate authentication logs, identify vulnerable assets, review security events, and analyze organizational data stored in relational databases.

---

# Why It Matters

Security analysts frequently query databases to:

- Investigate login activity
- Review endpoint inventories
- Identify outdated operating systems
- Analyze authentication events
- Search for compromised accounts
- Generate audit reports

Understanding how to retrieve data efficiently is one of the most valuable SQL skills for cybersecurity professionals.

---

# Basic SELECT Statement

Retrieve all columns from a table.

### Syntax

```sql
SELECT *
FROM table_name;
```

### Example

```sql
SELECT *
FROM machines;
```

The asterisk (`*`) returns every column in the table.

---

# Selecting Specific Columns

Retrieve only the columns you need.

### Syntax

```sql
SELECT column1, column2
FROM table_name;
```

### Example

```sql
SELECT device_id, email_client
FROM machines;
```

Output

| device_id | email_client |
|------------|--------------|
| a184b775c707 | Email Client 1 |
| a192b174c940 | Email Client 1 |

Selecting only the required columns improves readability and query efficiency.

---

# Selecting Multiple Columns

Example

```sql
SELECT device_id,
       operating_system,
       OS_patch_date
FROM machines;
```

Example Output

| Device | Operating System | Patch Date |
|---------|------------------|------------|
| a184b775c707 | OS 1 | 2021-09-01 |

---

# Investigating Login Activity

Example

```sql
SELECT event_id,
       country
FROM log_in_attempts;
```

This query allows analysts to review login attempts by geographic location.

Possible indicators include:

- Unexpected countries
- Impossible travel
- Foreign logins

---

Another example

```sql
SELECT username,
       login_date,
       login_time
FROM log_in_attempts;
```

Useful for investigating:

- Late-night logins
- Unusual authentication patterns
- Account compromise

---

# Selecting Every Column

```sql
SELECT *
FROM log_in_attempts;
```

Although useful while learning, production environments typically retrieve only the columns required.

---

# ORDER BY

Sorts query results.

### Syntax

```sql
SELECT *
FROM table
ORDER BY column;
```

Example

```sql
SELECT *
FROM log_in_attempts
ORDER BY login_date;
```

---

## Sorting by Multiple Columns

```sql
SELECT *
FROM log_in_attempts
ORDER BY login_date,
         login_time;
```

SQL sorts the first column before moving to the second.

---

# SQL Syntax Rules

Every query follows the same general structure.

```sql
SELECT columns
FROM table
ORDER BY column;
```

Statements end with a semicolon.

---

# Lab Summary

During this lab I practiced:

- Retrieving all records from a table
- Selecting specific columns
- Selecting multiple columns
- Investigating login activity
- Reviewing endpoint inventory
- Sorting query results
- Ordering results using multiple columns

---

# Practical Cybersecurity Uses

These SQL queries are commonly used to:

- Investigate authentication logs
- Identify vulnerable endpoints
- Review patch management
- Audit login activity
- Detect suspicious geographic logins
- Generate security reports
- Analyze organizational assets

---

# Key Takeaways

- `SELECT` retrieves data.
- `FROM` specifies the table.
- `*` returns every column.
- Listing column names returns only selected data.
- `ORDER BY` sorts query results.
- Multiple columns can be used for chronological sorting.

---

# Skills Practiced

- SQL
- Database Queries
- Data Retrieval
- Data Analysis
- Security Investigations
- Authentication Analysis
- Asset Management
- Query Optimization
