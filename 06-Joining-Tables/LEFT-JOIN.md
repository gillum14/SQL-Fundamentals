# LEFT JOIN

## Overview

A `LEFT JOIN` returns **every record from the left table**, along with matching records from the right table.

If no matching record exists in the right table, SQL returns **NULL** for the missing values.

---

## Syntax

```sql
SELECT columns
FROM table1
LEFT JOIN table2
ON table1.column = table2.column;
```

---

## Example

Return every machine, even if it is not assigned to an employee.

```sql
SELECT *
FROM machines
LEFT JOIN employees
ON machines.device_id = employees.device_id;
```

---

## Visual Representation

```
Machines          Employees

██████████████████
███████
███████

Everything from Machines is returned.
Missing employees appear as NULL.
```

---

## Example Result

| Device | Username |
|---------|----------|
| Laptop01 | jsmith |
| Laptop02 | NULL |
| Laptop03 | cjohnson |

---

## Practical Cybersecurity Uses

- Find unassigned devices
- Audit hardware inventory
- Identify orphaned assets
- Verify asset management records

---

## Key Takeaways

- Keeps every row from the left table.
- Missing matches become NULL.
- Excellent for finding missing relationships.
