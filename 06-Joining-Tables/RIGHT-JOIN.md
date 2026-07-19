# RIGHT JOIN

## Overview

A `RIGHT JOIN` returns **every record from the right table**, along with matching records from the left table.

If no matching record exists in the left table, SQL returns **NULL** for the missing values.

---

## Syntax

```sql
SELECT columns
FROM table1
RIGHT JOIN table2
ON table1.column = table2.column;
```

---

## Example

Return every employee, even if they do not have an assigned machine.

```sql
SELECT *
FROM machines
RIGHT JOIN employees
ON machines.device_id = employees.device_id;
```

---

## Visual Representation

```
Machines          Employees

         ██████████████████
               ███████
               ███████

Everything from Employees is returned.
Missing machines appear as NULL.
```

---

## Example Result

| Username | Device |
|----------|--------|
| jsmith | Laptop01 |
| cjohnson | Laptop05 |
| areyes | NULL |

---

## Industry Tip

Although SQL supports `RIGHT JOIN`, many professionals rarely use it.

Instead of writing:

```sql
FROM machines
RIGHT JOIN employees
```

Most analysts simply reverse the table order and use:

```sql
FROM employees
LEFT JOIN machines
```

Both queries produce the same result, but `LEFT JOIN` is generally considered easier to read and is more common in professional environments.

---

## Practical Cybersecurity Uses

- Find users without assigned devices
- Audit user provisioning
- Verify onboarding processes
- Identify account inconsistencies

---

## Key Takeaways

- Keeps every row from the right table.
- Missing matches become NULL.
- Often replaced with an equivalent LEFT JOIN by reversing table order.
