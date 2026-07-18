# learn-sql-with-phoebe - official course map

**Course:** learn-sql-with-phoebe, a two-track interactive SQL course by Phoebe Fu.
**Running project:** Daybreak, a DTC coffee-subscription brand. One SQLite database
(`customers`, `products`, `orders`, `order_items`, `subscriptions`, `events`) queried across
every session, harder each time. It runs live in the browser via sql.js (SQLite compiled to
WebAssembly, vendored in `assets/`), so every example is an editable, runnable playground with
no server and no login.

**Two tracks:**
- **Leader track (a1-a6, 6 x 45 min):** for C-level, managers, non-coders. Read and judge SQL,
  never write production queries. Exec thinking-mode.
- **Builder track (b1-b10, 10 x 45 min):** for practitioners. Hands-on, from first SELECT to
  window functions, a real revenue-drop investigation, and production warehouses.

## The 80% bar (honest coverage)

Each session teaches roughly 80% of its mapped sources' **working query content**, run on live
data instead of static screenshots. What stays on the official sites, by design:
certificates, graded problem sets / auto-checked exercises, video lectures, and vendor-specific
setup (e.g. Kaggle's BigQuery accounts). Each session page links its sources and says so plainly.

## Sources (verified by live fetch, 2026-07-18)

| Source | URL | What it is | Access |
|---|---|---|---|
| Mode SQL Tutorial | mode.com/sql-tutorial | Basic (15) + Intermediate (~21) + Advanced (9) + Analytics Training case track (8) | Free, in-browser editor |
| SQLBolt | sqlbolt.com | 18 interactive lessons + review + capstone | Free, no login |
| SQLZoo | sqlzoo.net | 16 tutorial modules | Free, no login |
| Kaggle Intro to SQL | kaggle.com/learn/intro-to-sql | 6 lessons (BigQuery dialect) | Free login, notebooks |
| Kaggle Advanced SQL | kaggle.com/learn/advanced-sql | 4 lessons (BigQuery, incl. Analytic Functions) | Free login, notebooks |
| Khan Academy Intro to SQL | khanacademy.org/computing/computer-programming/sql | 4 units (SQLite, video + challenges) | Free |
| W3Schools SQL | w3schools.com/sql | ~65 topic pages (ANSI/MySQL-flavored) | Free, open |

Dialect note: this course teaches **SQLite** (it compiles to WASM, which is why the playground
works). ~90% of the language is identical across Postgres/MySQL/BigQuery/Snowflake; session b10
carries the full dialect-delta table.

## Builder track coverage map

| # | Session | Teaches | Sources (✓ core / ◐ partial) |
|---|---------|---------|------------------------------|
| b1 | Meet your database | SELECT, FROM, LIMIT, ORDER BY, schema, the playground | Mode Basic ✓, SQLBolt L1 ✓, Khan U1 ◐, W3Schools Intro/Select ◐ |
| b2 | Filtering rows | WHERE, comparison + logical operators, LIKE, IN, BETWEEN, IS NULL | Mode Basic ✓, SQLBolt L2-4 ✓, W3Schools Where/Like/In/Between/Null ◐ |
| b3 | Aggregating | COUNT/SUM/AVG/MIN/MAX, GROUP BY, HAVING, DISTINCT | Mode Intermediate ✓, SQLBolt L10-11 ✓, Kaggle Intro L3 ◐ |
| b4 | Joining tables | INNER/LEFT (+RIGHT/FULL note), chaining, self-join | Mode Joins ✓, SQLZoo JOIN/More JOIN ✓, Kaggle Intro L6 ◐ |
| b5 | Combining + reshaping | CASE, aliases/expressions, string + date functions, UNION | Mode Advanced ✓, Mode UNION ✓, W3Schools Case/Union/Aliases ◐ |
| b6 | Subqueries + CTEs | scalar/IN subqueries, WITH clauses | Mode Advanced Subqueries ✓, SQLZoo SELECT-within-SELECT ✓, Kaggle Intro As&With ◐ |
| b7 | Window functions | ROW_NUMBER/RANK/DENSE_RANK, LAG/LEAD, running totals, PARTITION BY | Mode Window ✓, SQLZoo Window ✓, Kaggle Adv Analytic Functions ◐ |
| b8 | Building + changing data | CREATE/ALTER/DROP, PK/FK, INSERT/UPDATE/DELETE, order of execution | SQLBolt L13-18 ✓, W3Schools SQL Database ✓, SQLBolt L12 ◐ |
| b9 | Analyst case study | end-to-end investigation of the March revenue drop, cohort peek | Mode Analytics Training ✓, applies b1-b7 ✓ |
| b10 | Performance + warehouses | EXPLAIN QUERY PLAN, indexes, dialect deltas, SQLite→prod | Mode Performance ✓, Kaggle Adv Efficient Queries ✓, dialect refs ◐ |

## Leader track coverage map

| # | Session | Teaches | Maps to |
|---|---------|---------|---------|
| a1 | What SQL actually is | databases as tables, SQL as the question layer, metric = a query | Mode Intro framing ✓, SQLBolt/Khan reading level ◐ |
| a2 | Reading a query without fear | SELECT/FROM/WHERE/GROUP BY in business terms, what a JOIN means | Mode Basic/Intermediate reading ✓, Khan ◐ |
| a3 | Judging a data claim | count vs sum vs avg, "per what", the refund trap | Mode aggregates conceptually ✓, decision-intelligence ◐ |
| a4 | The dashboard behind the dashboard | every KPI is a query, cohort vs snapshot, denominators | BI concepts ✓, Mode analytics framing ◐ |
| a5 | Asking for the right cut | the 5-part data request, defining metrics, request etiquette | analyst-collaboration best practice ✓ |
| a6 | SQL, warehouses & AI | modern stack, text-to-SQL, governance, what to invest in | modern data stack ✓, governance/semantic-layer ◐ |

## Not covered by design (stays official)

- Certificates and completion badges (Kaggle, W3Schools exam).
- Auto-graded exercise checkers (SQLBolt, SQLZoo, LeetCode/StrataScratch/DataLemur practice banks).
- Video lectures (Khan Academy).
- BigQuery account setup and BigQuery-only features (Kaggle's nested/repeated data, `project.dataset.table`).
- Deep DB administration (users, permissions, backups, replication) - out of scope for both tracks.

## Overlap discipline

Mode, SQLBolt, SQLZoo, Khan and W3Schools share a large common core (SELECT → WHERE → aggregates
→ JOIN → subqueries). That shared core is taught **once** on live Daybreak data; per-source
extras (Mode's Analytics Training case, Kaggle's analytic functions, W3Schools' DDL depth) are
folded into the session where they fit. Practice-bank sites (LeetCode SQL 50, StrataScratch,
DataLemur) are linked as next-step drilling, not re-taught.

## Re-verify before delivery

SQL curricula move slowly, but Mode now redirects to ThoughtSpot and Kaggle occasionally
reorders lessons. Re-check source URLs before any major re-share.
