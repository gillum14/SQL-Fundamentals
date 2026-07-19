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

### Syntax

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

### Syntax

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

# Equality Operator (`=`)

Find exact matches.

### Example

```sql
SELECT *
FROM employees
WHERE department = 'Finance';
```

---

Another example

```sql
SELECT *
FROM employees
WHERE office = 'South-109';
```

---

# LIKE

Searches for text patterns.

### Syntax

```sql
WHERE column LIKE pattern;
```

---

## Using `%`

The percent sign (`%`) represents zero or more characters.

Example

```sql
WHERE office LIKE 'South%';
```

Matches

```text
South-109
South-210
South-315
```

---

Example

```sql
WHERE office LIKE '%South';
```

Matches

```text
Office-South
Building-South
```

---

Example

```sql
WHERE office LIKE '%South%';
```

Matches any value containing the word **South**.

---

# Common Filtering Examples

Retrieve all Finance employees.

```sql
SELECT *
FROM employees
WHERE department = 'Finance';
```

---

Retrieve all Sales employees.

```sql
SELECT *
FROM employees
WHERE department = 'Sales';
```

---

Retrieve machines running OS 2.

```sql
SELECT device_id,
       operating_system
FROM machines
WHERE operating_system = 'OS 2';
```

---

Find a specific office.

```sql
SELECT *
FROM employees
WHERE office = 'South-109';
```

---

Find every employee in the South building.

```sql
SELECT *
FROM employees
WHERE office LIKE 'South%';
```

---

# Exact Match vs Pattern Matching

Exact Match

```sql
WHERE department = 'Finance'
```

Returns only rows where the value is exactly **Finance**.

---

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

The `WHERE` clause filters records **before** sorting occurs.

---

# Lab Summary

During this lab I practiced:

- Exploring table structures
- Filtering records with `WHERE`
- Finding exact matches
- Using `LIKE`
- Searching with wildcard patterns
- Identifying vulnerable systems
- Investigating employee information

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

---

# Key Takeaways

- `DESCRIBE` displays a table's structure.
- `WHERE` filters records based on specified conditions.
- `=` performs exact matching.
- `LIKE` searches for text patterns.
- `%` represents zero or more characters.
- Filtering significantly reduces the amount of data analysts need to review.

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
