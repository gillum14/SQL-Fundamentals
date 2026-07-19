# Logical Operators

## Overview

Logical operators combine multiple conditions into a single SQL query.

---

# AND

Every condition must be true.

```sql
SELECT *
FROM log_in_attempts
WHERE login_time > '18:00'
AND success = FALSE;
```

Another example

```sql
SELECT *
FROM employees
WHERE department = 'Marketing'
AND office LIKE 'East%';
```

---

# OR

At least one condition must be true.

```sql
SELECT *
FROM employees
WHERE department = 'Finance'
OR department = 'Sales';
```

Another example

```sql
SELECT *
FROM log_in_attempts
WHERE login_date = '2022-05-08'
OR login_date = '2022-05-09';
```

---

# NOT

Returns records that do not satisfy a condition.

```sql
SELECT *
FROM employees
WHERE NOT department = 'Information Technology';
```

Another example

```sql
SELECT *
FROM log_in_attempts
WHERE NOT country LIKE 'MEX%';
```

---

# Combining Operators

Example

```sql
SELECT *
FROM log_in_attempts
WHERE login_time > '18:00'
AND success = FALSE;
```

Example

```sql
SELECT *
FROM employees
WHERE department = 'Marketing'
AND office LIKE 'East%';
```

---

# Practical Cybersecurity Uses

- Investigating failed logins
- Reviewing after-hours access
- Searching multiple departments
- Excluding trusted countries
- Threat hunting
- Authentication analysis

---

# Key Takeaways

- `AND` requires every condition to be true.
- `OR` requires at least one condition to be true.
- `NOT` excludes matching records.
- Logical operators can be combined to create highly targeted queries.
