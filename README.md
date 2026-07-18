# learn-sql-with-phoebe

A two-track, interactive SQL course you run **in your browser** - no install, no login, no server.
Every example is a live, editable SQL editor running real SQLite (via [sql.js](https://github.com/sql-js/sql.js),
vendored locally) against one small database: **Daybreak**, a direct-to-consumer coffee-subscription brand.

By Phoebe Fu.

## Two tracks

- **🤝 Leader track (a1-a6)** - for C-level, managers, and non-coders. Learn to *read*, *question*,
  and *commission* SQL without writing production queries. Six 45-minute sessions.
- **🛠️ Builder track (b1-b10)** - for practitioners. From your first `SELECT` to window functions,
  a real revenue-drop investigation, and production warehouses. Ten 45-minute sessions.

Start at [`index.html`](index.html).

## The running database: Daybreak

Six linked tables queried across every session, harder each time:
`customers`, `products`, `orders`, `order_items`, `subscriptions`, `events`.
The schema and seed live in [`assets/daybreak-seed.js`](assets/daybreak-seed.js) - a single source
of truth that every playground on every page loads a fresh copy of, so nothing you type can break
the next example.

## How the live playground works

`assets/sql-live.js` finds every `<div class="sqlbox">` on a page, turns it into an editable query
box, and runs it against a fresh seeded Daybreak database using SQLite compiled to WebAssembly.
It is fully client-side: after the one-time `sql-wasm.wasm` load there are zero network calls, which
is why it works on plain GitHub Pages. Press **▶ Run** (or Cmd/Ctrl+Enter).

## Built from official curricula

Taught from the working core of Mode, SQLBolt, SQLZoo, Kaggle (Intro + Advanced), Khan Academy,
and W3Schools. See [`materials/official-course-map.md`](materials/official-course-map.md) for the
per-session coverage map and the honest "what stays on the official sites" list.

## Structure

```
index.html                     two-track landing + knowledge mindmap
courses/a1..a6-*.html          leader track
courses/b1..b10-*.html         builder track
assets/style.css               editorial-bold design system (SQLite blue)
assets/app.js                  engagement layer (progress, journey, quizzes, zoom)
assets/mindmap.js              the knowledge map on the landing page
assets/sql-live.js             the live SQL playground engine
assets/daybreak-seed.js        the Daybreak database (schema + seed)
assets/sql-wasm.js / .wasm     sql.js (SQLite in WebAssembly), vendored
materials/official-course-map.md   source coverage map
```

## Local preview

```bash
python3 -m http.server 8000
# then open http://localhost:8000
```
