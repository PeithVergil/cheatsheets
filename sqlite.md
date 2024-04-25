sqlite3
=======

Open a database (mydatabase.db).

```bash
sqlite3 mydatabase.db

# Better output formatting
sqlite3 -table mydatabase.db
sqlite3 -column -header mydatabase.db
```

List tables.

```bash
.tables
```

Describe a table (mytable).

```bash
.schema mytable
```

Quiting the `sqlite3` client.

```bash
.quit
```