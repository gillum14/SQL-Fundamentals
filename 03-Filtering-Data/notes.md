# Filtering Data

## Overview

The `WHERE` clause allows SQL queries to return only the records that match specified conditions. Instead of retrieving every row in a table, filtering narrows the results to the information that is relevant to an investigation.

Filtering data is one of the most important SQL skills for cybersecurity professionals because security investigations often involve searching through large datasets for specific users, devices, login attempts, or suspicious activity.

---

# Why It Matters

Security analysts use filtering to:

- Investigate suspicious login attempts
- Identify vulnerable devices
- Locate compromised user accounts
- Search for failed authentication events
- Review systems requiring updates
- Generate targeted security reports

Without filtering, analysts would need to manually review thousands or even millions of records.

---

# DESCRIBE

Displays the structure of a database table.

## Syntax

```sql
DESCRIBE table_name;
```

### Example

```sql
DESCRIBE machines;
```

Example Output

| Field | Type |
|---------|------|
| device_id | varchar |
| operating_system | varchar |
| employee_id | int |

### Common Uses

- View available columns
- Verify data types
- Learn table structure before writing queries

---

# WHERE

Filters rows returned by a query.

## Syntax

```sql
SELECT columns
FROM table
WHERE condition;
```

### Example

```sql
SELECT device_id,
       operating_system
FROM machines
WHERE operating_system = 'OS 2';
```

Only rows matching the condition are returned.

---

# Comparison Operators

Comparison operators allow SQL to compare values and return only matching records.

| Operator | Meaning |
|-----------|---------|
| = | Equal |
| != | Not Equal |
| <> | Not Equal |
| > | Greater Than |
| >= | Greater Than or Equal |
| < | Less Than |
| <= | Less Than or Equal |

---

# Equality Operator (=)

Find exact matches.

```sql
SELECT *
FROM employees
WHERE department = 'Finance';
```

Another example

```sql
SELECT *
FROM employees
WHERE office = 'South-109';
```

---

# Greater Than (>)

Returns values greater than the specified value.

```sql
SELECT *
FROM log_in_attempts
WHERE login_date > '2023-01-15';
```

Common Uses

- Recent login attempts
- Newly created accounts
- Devices patched after a certain date
- Security events after an incident

---

# Greater Than or Equal (>=)

Includes the specified value.

```sql
SELECT *
FROM log_in_attempts
WHERE login_date >= '2023-01-15';
```

---

# Less Than (<)

Returns values before the specified value.

```sql
SELECT *
FROM log_in_attempts
WHERE login_date < '2023-01-15';
```

Useful for investigating historical events.

---

# Less Than or Equal (<=)

Includes the specified value.

```sql
SELECT *
FROM log_in_attempts
WHERE login_date <= '2023-01-15';
```

---

# BETWEEN

Returns values inside an inclusive range.

## Syntax

```sql
WHERE column
BETWEEN value1
AND value2;
```

### Example

```sql
SELECT *
FROM log_in_attempts
WHERE login_date
BETWEEN '2023-02-01'
AND '2023-02-07';
```

`BETWEEN` includes both the beginning and ending values.

---

# LIKE

Searches for text patterns.

## Syntax

```sql
WHERE column LIKE pattern;
```

---

## Using %

The percent sign (`%`) represents zero or more characters.

### Starts With

```sql
WHERE office LIKE 'South%';
```

Matches

```
South-109
South-210
South-315
```

---

### Ends With

```sql
WHERE office LIKE '%South';
```

Matches

```
Office-South
Building-South
```

---

### Contains

```sql
WHERE office LIKE '%South%';
```

Matches any value containing **South**.

---

# Filtering by Time

Search for events occurring at an exact time.

```sql
SELECT *
FROM log_in_attempts
WHERE login_time = '09:30:00';
```

Useful when:

- Investigating suspicious login activity
- Correlating SIEM alerts
- Matching firewall logs
- Reviewing authentication events

---

# Filtering by ID

Retrieve one specific record.

```sql
SELECT *
FROM log_in_attempts
WHERE login_id = 503;
```

Common identifiers include:

- login_id
- employee_id
- event_id
- device_id

---

# Common Filtering Examples

Retrieve all Finance employees.

```sql
SELECT *
FROM employees
WHERE department = 'Finance';
```

Retrieve all Sales employees.

```sql
SELECT *
FROM employees
WHERE department = 'Sales';
```

Retrieve machines running OS 2.

```sql
SELECT device_id,
       operating_system
FROM machines
WHERE operating_system = 'OS 2';
```

Find a specific office.

```sql
SELECT *
FROM employees
WHERE office = 'South-109';
```

Find every employee in the South building.

```sql
SELECT *
FROM employees
WHERE office LIKE 'South%';
```

Find login attempts after a date.

```sql
SELECT *
FROM log_in_attempts
WHERE login_date > '2023-01-15';
```

Find login attempts during a specific date range.

```sql
SELECT *
FROM log_in_attempts
WHERE login_date
BETWEEN '2023-02-01'
AND '2023-02-07';
```

Find a specific login time.

```sql
SELECT *
FROM log_in_attempts
WHERE login_time = '09:30:00';
```

Find a specific login ID.

```sql
SELECT *
FROM log_in_attempts
WHERE login_id = 503;
```

---

# Exact Match vs Pattern Matching

Exact Match

```sql
WHERE department = 'Finance'
```

Returns only rows where the value is exactly **Finance**.

Pattern Match

```sql
WHERE office LIKE 'South%'
```

Returns every office beginning with **South**.

---

# SQL Query Flow

```sql
SELECT columns
FROM table
WHERE condition
ORDER BY column;
```

The `WHERE` clause filters records before sorting occurs.

---

# Practical Cybersecurity Uses

Filtering data is commonly used to:

- Investigate authentication events
- Identify outdated operating systems
- Search for compromised user accounts
- Find devices requiring security updates
- Review access by department
- Investigate physical office locations
- Search SIEM exports
- Analyze endpoint inventories
- Review security events after a specific date
- Investigate suspicious login times
- Locate individual events by unique identifier

---

# Example Investigation Queries

Recent logins

```sql
SELECT username, login_date
FROM log_in_attempts
WHERE login_date > '2025-01-01';
```

Specific employee

```sql
SELECT *
FROM employees
WHERE employee_id = 1024;
```

Events during an incident

```sql
SELECT *
FROM log_in_attempts
WHERE login_date
BETWEEN '2025-03-01'
AND '2025-03-02';
```

Late-night logins

```sql
SELECT *
FROM log_in_attempts
WHERE login_time > '22:00:00';
```

Failed logins from outside the United States

```sql
SELECT *
FROM log_in_attempts
WHERE success = FALSE
AND country != 'USA';
```

---

# Lab Summary

During this chapter I practiced:

- Exploring table structures with `DESCRIBE`
- Filtering records with `WHERE`
- Finding exact matches
- Using comparison operators
- Filtering by date
- Filtering by time
- Filtering by unique identifiers
- Using `BETWEEN`
- Using `LIKE`
- Searching with wildcard patterns
- Investigating employee information
- Identifying vulnerable systems

---

# Key Takeaways

- `DESCRIBE` displays a table's structure.
- `WHERE` filters records based on specified conditions.
- Comparison operators allow filtering by numeric, date, and time values.
- `BETWEEN` filters inclusive ranges.
- `LIKE` performs pattern matching.
- `%` represents zero or more characters.
- Filtering dramatically reduces the amount of data analysts need to review.
- Filtering is one of the most frequently used SQL techniques during security investigations.

---

# Skills Practiced

- SQL
- Data Filtering
- Query Construction
- Database Analysis
- Pattern Matching
- Asset Management
- Security Investigations
- Log Analysis
- Threat Hunting
- Authentication Analysis
