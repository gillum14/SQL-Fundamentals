# Comparison Operators

## Overview

Comparison operators compare values and return only records that satisfy the specified condition.

---

# Operators

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

# Examples

After a date

```sql
WHERE login_date > '2023-01-15'
```

On or after

```sql
WHERE login_date >= '2023-01-15'
```

Before

```sql
WHERE login_date < '2023-01-15'
```

On or before

```sql
WHERE login_date <= '2023-01-15'
```

Inclusive range

```sql
WHERE login_date
BETWEEN '2023-02-01'
AND '2023-02-07'
```

Specific login time

```sql
WHERE login_time = '09:30:00'
```

Specific login ID

```sql
WHERE login_id = 503
```

---

# BETWEEN

`BETWEEN` returns values within an inclusive range.

```sql
SELECT *
FROM log_in_attempts
WHERE login_date
BETWEEN '2023-02-01'
AND '2023-02-07';
```

---

# Practical Cybersecurity Uses

- Timeline analysis
- Incident investigations
- Authentication analysis
- Compliance reporting

---

# Key Takeaways

- Comparison operators compare values.
- `BETWEEN` includes both endpoints.
- Dates, times, and numbers can all be compared.
