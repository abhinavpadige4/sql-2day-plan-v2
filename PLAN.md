# 2-Day SQL Study Plan

A tight, two-day plan that takes you from "I know SELECT" to "I can solve
typical SQL interview questions". Every topic is paired with a solved practice
query in this repo so you can verify your understanding immediately.

---

## Goals

By the end of Day 2 you should be able to:

- Write correct `SELECT` / `WHERE` / `GROUP BY` / `HAVING` queries from scratch.
- Choose the right JOIN type (INNER, LEFT, RIGHT, FULL) for a given question.
- Write scalar, IN, EXISTS, and correlated subqueries.
- Use window functions (`ROW_NUMBER`, `RANK`, `DENSE_RANK`, `LAG`, `LEAD`,
  running totals) to solve "top-N per group" and "running total" problems.
- Structure complex queries with CTEs (`WITH`) for readability.
- Explain your SQL out loud — what each clause does and why.

---

## Day 1 — Foundations

**Theme:** Single-table queries, filtering, aggregation, and string/date
manipulation. This is the 80% of SQL you'll use every day.

### Morning (90 min)

1. **SELECT & aliases** — pick columns, rename them with `AS`.
   - Practice: `day1/01_basic_select.sql`
2. **WHERE** — `=`, `<>`, `<`, `>`, `BETWEEN`, `IN`, `LIKE`, `IS NULL`.
   - Practice: `day1/02_where_filters.sql`
3. **ORDER BY** — single and multi-column sorting, `ASC` / `DESC`.
   - Practice: `day1/03_order_by.sql`

### Afternoon (90 min)

4. **Aggregates** — `COUNT`, `SUM`, `AVG`, `MIN`, `MAX`, `COUNT(DISTINCT ...)`.
   - Practice: `day1/04_aggregates.sql`
5. **GROUP BY + HAVING** — the #1 source of confusion. Rule: every non-aggregated
   column in `SELECT` must appear in `GROUP BY`.
   - Practice: `day1/05_group_by_having.sql`
6. **DISTINCT & NULLs** — how `NULL` behaves in comparisons and aggregates.
   - Practice: `day1/06_distinct_nulls.sql`
7. **Strings & CASE** — `CONCAT`, `SUBSTRING`, `UPPER`, `LOWER`, `CASE WHEN`.
   - Practice: `day1/07_strings_case.sql`
8. **Dates** — `DATE_TRUNC`, `EXTRACT`, date arithmetic, ranges.
   - Practice: `day1/08_dates.sql`

### Evening (15 min)

- Re-run every query from Day 1 from memory. Anything you can't reproduce,
  re-read the comments.

---

## Day 2 — Intermediate

**Theme:** Multi-table queries, subqueries, window functions, and CTEs.
This is where interview questions live.

### Morning (90 min)

9. **Joins** — INNER, LEFT, RIGHT, FULL. Know the difference between
   "no match" (LEFT) and "must match" (INNER).
   - Practice: `day2/09_joins.sql`
10. **Self-join** — employees reporting to managers.
    - Practice: `day2/10_self_join.sql`
11. **Subqueries** — scalar, `IN`, and correlated.
    - Practice: `day2/11_subqueries.sql`
12. **EXISTS vs IN** — when to use which, and the NULL trap.
    - Practice: `day2/12_exists_vs_in.sql`
13. **Ranking windows** — `ROW_NUMBER`, `RANK`, `DENSE_RANK`.
    - Practice: `day2/13_window_ranking.sql`

### Afternoon (75 min)

14. **Running totals & LAG/LEAD** — cumulative sums, period-over-period.
    - Practice: `day2/14_window_running.sql`
15. **Top-N per group** — the classic interview problem.
    - Practice: `day2/15_top_n_per_group.sql`
16. **CTEs & recursive CTEs** — readability + hierarchy traversal.
    - Practice: `day2/16_ctes.sql`
17. **UNION / UNION ALL** — combining result sets.
    - Practice: `day2/17_union.sql`

### Capstone (30 min, timed)

18. **Interview problem: monthly revenue per country.**
    - Practice: `day2/18_interview_revenue_by_month.sql`

---

## Common pitfalls to watch for

- **`WHERE` vs `HAVING`** — `WHERE` filters rows *before* grouping; `HAVING`
  filters *after* grouping.
- **`NULL` in joins** — `NULL = NULL` is not true. Use `IS NULL` or `COALESCE`.
- **`COUNT(*)` vs `COUNT(col)`** — `COUNT(*)` counts rows; `COUNT(col)` skips NULLs.
- **`RANK` vs `DENSE_RANK`** — `RANK` leaves gaps after ties; `DENSE_RANK` does not.
- **Correlated subqueries** — they run once per outer row; can be slow on big tables.
- **`UNION` vs `UNION ALL`** — `UNION` dedupes (slower); `UNION ALL` keeps duplicates.

---

## After the 2 days

- Pick 5 real interview questions (LeetCode SQL 50, StrataScratch, or your
  target company's past questions) and solve them cold.
- For each, write a one-paragraph explanation of your approach.
- Revisit this repo's `day2/` folder whenever you get stuck.
