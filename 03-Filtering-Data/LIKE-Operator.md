# LIKE Operator

## Overview

The `LIKE` operator searches for text patterns rather than exact values.

---

# Syntax

```sql
WHERE column LIKE pattern;
```

---

# Wildcards

## %

Matches zero or more characters.

Starts with

```sql
WHERE office LIKE 'South%'
```

Ends with

```sql
WHERE office LIKE '%South'
```

Contains

```sql
WHERE office LIKE '%South%'
```

---

## _

Matches exactly one character.

```sql
WHERE username LIKE 'J_n'
```

Matches

```
Jan
Jen
Jon
```

---

# Practical Cybersecurity Uses

- Search hostnames
- Search usernames
- Search departments
- Search office locations
- Search countries

---

# Key Takeaways

- `LIKE` performs pattern matching.
- `%` matches zero or more characters.
- `_` matches exactly one character.
