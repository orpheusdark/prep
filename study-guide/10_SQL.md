# 📁 FOLDER 10 — SQL ⭐ HIGH PRIORITY

---

## 🧠 CONCEPT OVERVIEW

SQL (Structured Query Language) is used to manage and query relational databases. Questions range from basic SELECT to complex window functions and CTEs.

---

## 📋 KEY RULES

| Category | Commands |
|----------|---------|
| DDL (Data Definition) | CREATE, ALTER, DROP, TRUNCATE |
| DML (Data Manipulation) | INSERT, UPDATE, DELETE |
| DQL (Data Query) | SELECT |
| DCL (Data Control) | GRANT, REVOKE |
| TCL (Transaction Control) | COMMIT, ROLLBACK, SAVEPOINT |

---

## ❓ QUESTIONS + SOLUTIONS

---

### Q1. Primary Key vs Foreign Key ⭐

| Feature | Primary Key | Foreign Key |
|---------|-------------|-------------|
| Purpose | Uniquely identifies a row | References primary key in another table |
| Null? | Never null | Can be null |
| Duplicates? | Never | Allowed |
| Table | Any | Child table |

**Candidate Key:** Any column(s) that could serve as a primary key (uniquely identifies rows).

---

### Q2. What is Normalization? ⭐

**Definition:** Organizing database tables to reduce data redundancy and improve integrity.

| Normal Form | Rule |
|------------|------|
| 1NF | All columns are atomic (no repeating groups) |
| 2NF | 1NF + no partial dependency on composite key |
| 3NF | 2NF + no transitive dependency |

---

### Q3. JOIN Types ⭐ 🔥 MUST KNOW

```sql
-- INNER JOIN: Only rows with matches in BOTH tables
SELECT e.name, d.dept_name
FROM employees e
INNER JOIN departments d ON e.dept_id = d.id;

-- LEFT JOIN: All rows from LEFT table + matched from right (NULL if no match)
SELECT e.name, d.dept_name
FROM employees e
LEFT JOIN departments d ON e.dept_id = d.id;

-- RIGHT JOIN: All rows from RIGHT table + matched from left
-- FULL OUTER JOIN: All rows from both tables
```

**Visual:**
```
INNER JOIN  = A ∩ B (intersection only)
LEFT JOIN   = All A + matched B (unmatched B = NULL)
RIGHT JOIN  = All B + matched A (unmatched A = NULL)
FULL OUTER  = All A + All B (unmatched = NULL)
```

**Self Join:** A table joins itself. Used to compare rows in the same table.
```sql
-- Employees who earn more than their manager
SELECT e.name, e.salary
FROM employees e
INNER JOIN employees m ON e.manager_id = m.id
WHERE e.salary > m.salary;
```

---

### Q4. GROUP BY vs HAVING vs WHERE ⭐ 🔥

```sql
SELECT dept_id, AVG(salary) as avg_sal
FROM employees
WHERE salary > 30000          -- filters ROWS (before grouping)
GROUP BY dept_id              -- groups rows
HAVING AVG(salary) > 50000;  -- filters GROUPS (after grouping)
```

**Rule:**
- `WHERE` → before aggregation → filters rows
- `HAVING` → after aggregation → filters groups

**🧠 Remember:** WHERE = rows filter, HAVING = group filter

---

### Q5. Aggregate Functions ⭐

| Function | Purpose |
|---------|---------|
| `COUNT(*)` | Count rows |
| `SUM(col)` | Sum of values |
| `AVG(col)` | Average |
| `MAX(col)` | Maximum |
| `MIN(col)` | Minimum |

```sql
-- Find highest salary per department
SELECT dept_id, MAX(salary) as max_sal
FROM employees
GROUP BY dept_id;

-- Departments with more than 5 employees
SELECT dept_id, COUNT(*) as emp_count
FROM employees
GROUP BY dept_id
HAVING COUNT(*) > 5;
```

---

### Q6. Find Second Highest Salary ⭐ 🔥 MUST KNOW

```sql
-- Method 1: Subquery (classic)
SELECT MAX(salary)
FROM employees
WHERE salary < (SELECT MAX(salary) FROM employees);

-- Method 2: Using LIMIT/OFFSET
SELECT DISTINCT salary
FROM employees
ORDER BY salary DESC
LIMIT 1 OFFSET 1;

-- Method 3: Window function (best for N-th highest)
SELECT salary FROM (
  SELECT salary, DENSE_RANK() OVER (ORDER BY salary DESC) as rnk
  FROM employees
) t WHERE rnk = 2;
```

---

### Q7. Third Highest Salary WITHOUT LIMIT ⭐

```sql
SELECT MAX(salary)
FROM employees
WHERE salary NOT IN (
  SELECT TOP 2 salary FROM employees ORDER BY salary DESC
);
-- OR use DENSE_RANK as shown above with rnk = 3
```

---

### Q8. Find Duplicate Records ⭐

```sql
-- Find duplicates
SELECT name, COUNT(*) as count
FROM employees
GROUP BY name
HAVING COUNT(*) > 1;

-- Delete duplicates (keep one)
DELETE FROM employees
WHERE id NOT IN (
  SELECT MIN(id) FROM employees GROUP BY name
);
```

---

### Q9. Find Employees Earning More Than Average ⭐

```sql
SELECT name, salary
FROM employees
WHERE salary > (SELECT AVG(salary) FROM employees);
```

---

### Q10. Second Highest Salary Per Department ⭐

```sql
SELECT dept_id, salary FROM (
  SELECT dept_id, salary,
         DENSE_RANK() OVER (PARTITION BY dept_id ORDER BY salary DESC) as rnk
  FROM employees
) t WHERE rnk = 2;
```

---

### Q11. What is a Subquery? Correlated Subquery?

**Subquery:** A query inside another query.
```sql
SELECT name FROM employees WHERE salary > (SELECT AVG(salary) FROM employees);
```

**Correlated Subquery:** References the outer query. Re-executes for every row.
```sql
SELECT name, salary FROM employees e1
WHERE salary > (SELECT AVG(salary) FROM employees e2 WHERE e2.dept_id = e1.dept_id);
-- For each employee, compares to their own department's average
```

**Subquery vs CTE:**
| Feature | Subquery | CTE |
|---------|---------|-----|
| Readability | Lower (nested) | Higher (named, separated) |
| Reusability | No | Yes (reference multiple times) |
| Performance | Similar | Similar |

---

### Q12. CTE (Common Table Expression) ⭐

```sql
WITH DeptAvg AS (
  SELECT dept_id, AVG(salary) as avg_sal
  FROM employees
  GROUP BY dept_id
)
SELECT e.name, e.salary, d.avg_sal
FROM employees e
JOIN DeptAvg d ON e.dept_id = d.dept_id
WHERE e.salary > d.avg_sal;
```

**Definition:** A named temporary result set defined with `WITH`. Makes complex queries readable and reusable.

---

### Q13. Window Functions ⭐ 🔥 MUST KNOW

Window functions perform calculations across a set of rows related to the current row **without collapsing them** (unlike GROUP BY).

```sql
SELECT name, salary, dept_id,
  RANK()       OVER (PARTITION BY dept_id ORDER BY salary DESC) as rnk,
  DENSE_RANK() OVER (PARTITION BY dept_id ORDER BY salary DESC) as dense_rnk,
  ROW_NUMBER() OVER (PARTITION BY dept_id ORDER BY salary DESC) as row_num
FROM employees;
```

**Differences:**

| Function | Gaps for ties? | Example (ties at rank 2) |
|---------|---------------|--------------------------|
| `RANK()` | YES (1, 2, 2, **4**) | Skips 3 |
| `DENSE_RANK()` | NO (1, 2, 2, **3**) | No skips |
| `ROW_NUMBER()` | Unique always (1, 2, 3, 4) | No ties |

**🧠 Remember:**
- RANK = "competition rank" (ties skip numbers)
- DENSE_RANK = "dense/compact rank" (ties don't skip)
- ROW_NUMBER = always unique

**PARTITION BY** = like GROUP BY but within window (not collapsing rows)

---

### Q14. What is an Index? ⭐

**Definition:** A database structure that speeds up query lookup (like a book index).

**Advantages:** Faster SELECT/WHERE queries.
**Disadvantages:** Slower INSERT/UPDATE/DELETE (index must be updated too), extra storage.

**When can index HURT performance?**
- Small tables (scan is faster)
- Columns with low cardinality (e.g., gender — only 2 values)
- Frequent writes on the indexed column

**Composite index:** Index on multiple columns. Order matters!
```sql
CREATE INDEX idx_name ON employees (dept_id, salary);
-- Good for: WHERE dept_id = 5
-- Good for: WHERE dept_id = 5 AND salary > 50000
-- NOT used for: WHERE salary > 50000 alone (leftmost rule)
```

---

### Q15. Transactions & ACID ⭐

**Transaction:** A sequence of SQL operations treated as a single unit.

**ACID Properties:**

| Property | Meaning |
|---------|---------|
| **Atomicity** | All or nothing — if any step fails, whole transaction rolls back |
| **Consistency** | Data is always in a valid state |
| **Isolation** | Transactions don't interfere with each other |
| **Durability** | Once committed, changes are permanent (even after crash) |

**Database Deadlock:** Two transactions each wait for the other to release a lock → neither can proceed.

**🧠 Remember ACID:** "**A**ll **C**hanges **I**solated **D**urably" 

---

### Q16. Employees Who Joined in Last 6 Months ⭐

```sql
SELECT name, join_date
FROM employees
WHERE join_date >= DATEADD(MONTH, -6, GETDATE()); -- SQL Server
-- MySQL: WHERE join_date >= DATE_SUB(NOW(), INTERVAL 6 MONTH)
```

---

## 🔑 QUICK MEMORY TRICKS

- **JOIN types:** INNER=intersection, LEFT=all left+matched right, FULL=all
- **WHERE vs HAVING:** WHERE=rows before group, HAVING=groups after aggregate
- **Second highest:** `MAX WHERE salary < MAX(salary)` or `DENSE_RANK()=2`
- **RANK gaps**, **DENSE_RANK no gaps**, **ROW_NUMBER always unique**
- **ACID** = Atomicity Consistency Isolation Durability
- **Index** = speeds up reads, slows down writes

---

## ⚠️ COMMON MISTAKES

1. Using WHERE for aggregate conditions — use HAVING
2. Forgetting DISTINCT in "second highest salary" subquery approach
3. Confusing RANK (gaps) vs DENSE_RANK (no gaps)
4. Using PARTITION BY without understanding it groups for window functions only
5. Assuming index always makes queries faster — it can slow down writes
