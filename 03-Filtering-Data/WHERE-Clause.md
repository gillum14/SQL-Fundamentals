# WHERE Clause

## Overview

The `WHERE` clause filters records returned by a SQL query. Instead of retrieving every row from a table, `WHERE` limits results to only those that satisfy specified conditions.

---

# Syntax

```sql
SELECT columns
FROM table
WHERE condition;
```

---

# Examples

Retrieve Finance employees.

```sql
SELECT *
FROM employees
WHERE department = 'Finance';
```

Retrieve Sales employees.

```sql
SELECT *
FROM employees
WHERE department = 'Sales';
```

Retrieve machines running OS 2.

```sql
SELECT *
FROM machines
WHERE operating_system = 'OS 2';
```

Retrieve a specific office.

```sql
SELECT *
FROM employees
WHERE office = 'South-109';
```

---

# Common Uses

- Filter users
- Filter departments
- Filter operating systems
- Filter countries
- Filter dates
- Filter times

---

# Practical Cybersecurity Uses

- Investigate suspicious users
- Locate vulnerable endpoints
- Search authentication logs
- Review employee access

---

# Key Takeaways

- `WHERE` filters records.
- Only matching rows are returned.
- Filtering reduces the amount of data analysts must review.
