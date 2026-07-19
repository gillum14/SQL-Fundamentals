# INNER JOIN

## Overview

`INNER JOIN` returns only records that exist in **both** tables.

Rows without a matching value in the shared column are excluded from the results.

---

## Syntax

```sql
SELECT columns
FROM table1
INNER JOIN table2
ON table1.column = table2.column;
```

---

## Example

Match employees with their assigned machines.

```sql
SELECT *
FROM machines
INNER JOIN employees
ON machines.device_id = employees.device_id;
```

---

## Better Practice

Instead of using `SELECT *`, select only the columns you need.

```sql
SELECT
    employees.username,
    machines.device_id,
    machines.operating_system
FROM machines
INNER JOIN employees
ON machines.device_id = employees.device_id;
```

---

## Another Example

Retrieve login attempts made by employees.

```sql
SELECT *
FROM employees
INNER JOIN log_in_attempts
ON employees.username = log_in_attempts.username;
```

---

## Visual Representation

```
Employees        Machines

   ● ● ●            ● ● ●
     \              /
      \            /
       \__________/

Only matching records are returned.
```

---

## Practical Cybersecurity Uses

- Associate users with devices
- Match authentication logs to employees
- Investigate compromised systems
- Correlate multiple datasets

---

## Key Takeaways

- Returns only matching records.
- Requires a shared column.
- Most common join used during investigations.
