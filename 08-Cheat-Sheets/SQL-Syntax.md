# SQL Syntax Cheat Sheet

## Basic Query Structure

```sql
SELECT column_name
FROM table_name
WHERE condition
GROUP BY column_name
HAVING condition
ORDER BY column_name ASC;
```

> **SQL executes clauses in a different order than they are written.**

Execution Order:

1. `FROM`
2. `WHERE`
3. `GROUP BY`
4. `HAVING`
5. `SELECT`
6. `ORDER BY`
7. `LIMIT`

---

# SELECT

Retrieve data from a table.

```sql
SELECT *
FROM employees;
```

Retrieve specific columns.

```sql
SELECT employee_id, username
FROM employees;
```

---

# FROM

Specifies which table to query.

```sql
SELECT *
FROM login_attempts;
```

---

# WHERE

Filters records.

```sql
SELECT *
FROM employees
WHERE department = 'IT';
```

---

# ORDER BY

Sort results.

Ascending (default)

```sql
ORDER BY username;
```

Descending

```sql
ORDER BY username DESC;
```

Multiple columns

```sql
ORDER BY login_date, login_time;
```

---

# GROUP BY

Groups rows sharing the same value.

```sql
SELECT department, COUNT(*)
FROM employees
GROUP BY department;
```

---

# HAVING

Filters grouped data.

```sql
SELECT department, COUNT(*)
FROM employees
GROUP BY department
HAVING COUNT(*) > 10;
```

---

# LIMIT

Restrict number of rows returned.

```sql
SELECT *
FROM login_attempts
LIMIT 10;
```

---

# Comments

Single-line

```sql
-- This is a comment
```

Multi-line

```sql
/*
This is
a comment
*/
```

---

# Aliases

Rename columns.

```sql
SELECT username AS Employee
FROM employees;
```

Rename tables.

```sql
SELECT *
FROM employees AS e;
```

---

# Wildcard

Return every column.

```sql
SELECT *
FROM employees;
```

---

# SQL Formatting Best Practices

✔ Capitalize SQL keywords

```sql
SELECT username
FROM employees
WHERE department = 'IT'
ORDER BY username;
```

✔ One clause per line

✔ End every query with a semicolon

---

# Common Query Pattern

```sql
SELECT columns
FROM table
WHERE condition
ORDER BY column;
```

---

# SQL Clause Purpose

| Clause | Purpose |
|---------|----------|
| SELECT | Choose columns |
| FROM | Choose table |
| WHERE | Filter rows |
| GROUP BY | Group records |
| HAVING | Filter groups |
| ORDER BY | Sort results |
| LIMIT | Limit returned rows |

---

# Cybersecurity Uses

Security analysts commonly use SQL to:

- Investigate login attempts
- Search authentication logs
- Review endpoint inventories
- Analyze user activity
- Generate compliance reports
- Investigate security incidents
