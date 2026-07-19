# SQL Operators Cheat Sheet

## Comparison Operators

| Operator | Meaning |
|-----------|---------|
| `=` | Equal |
| `!=` | Not Equal |
| `<>` | Not Equal |
| `>` | Greater Than |
| `<` | Less Than |
| `>=` | Greater Than or Equal |
| `<=` | Less Than or Equal |

Example

```sql
WHERE failed_attempts > 5
```

---

# Logical Operators

## AND

Both conditions must be true.

```sql
WHERE department = 'IT'
AND status = 'Active'
```

---

## OR

At least one condition must be true.

```sql
WHERE country = 'Canada'
OR country = 'Mexico'
```

---

## NOT

Returns opposite condition.

```sql
WHERE NOT country = 'USA'
```

---

# LIKE

Search for patterns.

```sql
WHERE username LIKE 'a%'
```

---

## Wildcards

### %

Matches zero or more characters.

```sql
LIKE 'admin%'
```

Matches

```
admin
administrator
admin01
```

---

### _

Matches exactly one character.

```sql
LIKE 'J_n'
```

Matches

```
Jan
Jon
Jen
```

Does NOT match

```
John
```

---

# BETWEEN

Search within a range.

```sql
WHERE login_date
BETWEEN '2024-01-01'
AND '2024-12-31'
```

---

# IN

Matches multiple values.

```sql
WHERE department IN
('IT','HR','Security')
```

---

# IS NULL

Find missing values.

```sql
WHERE email IS NULL
```

---

# IS NOT NULL

Find populated values.

```sql
WHERE email IS NOT NULL
```

---

# DISTINCT

Remove duplicate values.

```sql
SELECT DISTINCT country
FROM login_attempts;
```

---

# COUNT

Count records.

```sql
SELECT COUNT(*)
FROM login_attempts;
```

---

# MIN / MAX

```sql
SELECT MIN(login_date)
FROM login_attempts;
```

```sql
SELECT MAX(login_date)
FROM login_attempts;
```

---

# AVG

Average value.

```sql
SELECT AVG(failed_attempts)
FROM logins;
```

---

# SUM

Add values together.

```sql
SELECT SUM(failed_attempts)
FROM logins;
```

---

# ORDER BY

Ascending

```sql
ORDER BY username ASC;
```

Descending

```sql
ORDER BY username DESC;
```

---

# Common WHERE Examples

Successful logins

```sql
WHERE success = TRUE
```

Failed logins

```sql
WHERE success = FALSE
```

Specific country

```sql
WHERE country = 'USA'
```

Multiple countries

```sql
WHERE country IN
('USA','Canada')
```

Outside the United States

```sql
WHERE country != 'USA'
```

Login after a specific date

```sql
WHERE login_date > '2025-01-01'
```

---

# Cybersecurity Examples

Find failed logins

```sql
SELECT *
FROM login_attempts
WHERE success = FALSE;
```

Find users outside the United States

```sql
SELECT username, country
FROM login_attempts
WHERE country != 'USA';
```

Sort newest logins first

```sql
SELECT *
FROM login_attempts
ORDER BY login_date DESC;
```

Find users in Security

```sql
SELECT *
FROM employees
WHERE department = 'Security';
```

---

# Operator Summary

| Operator | Purpose |
|-----------|----------|
| = | Equal |
| != / <> | Not Equal |
| > | Greater Than |
| < | Less Than |
| >= | Greater Than or Equal |
| <= | Less Than or Equal |
| AND | Both conditions true |
| OR | Either condition true |
| NOT | Opposite condition |
| LIKE | Pattern matching |
| % | Multiple characters |
| _ | Single character |
| BETWEEN | Range |
| IN | Multiple values |
| IS NULL | Missing values |
| IS NOT NULL | Existing values |
