# GpHero.sql

Database insights made easy

*A Greenplum version of [Ankane's awesome PgHero.sql](https://github.com/ankane/pghero)*

![Screenshot](https://pghero.herokuapp.com/assets/console-75e99c4a6e049943da6eba66b3d758e7.png)

Supports GreenPlum 4.2+

## Features

#### Queries

View all running queries with:

```sql
SELECT * FROM gphero_running_queries;
```

Queries running for longer than five minutes

```sql
SELECT * FROM gphero_long_running_queries;
```

Queries can be killed by `pid` with:

```sql
SELECT gphero_kill(123);
```

Kill all running queries with:

```sql
SELECT gphero_kill_all();
```

#### Index Usage

All usage

```sql
SELECT * FROM gphero_index_usage;
```

Missing indexes

```sql
SELECT * FROM gphero_missing_indexes;
```

Unused Indexes

```sql
SELECT * FROM gphero_unused_indexes;
```

#### Space

Largest tables and indexes

```sql
SELECT * FROM gphero_relation_sizes;
```

#### Cache Hit Ratio

```sql
SELECT gphero_index_hit_rate();
```

and

```sql
SELECT gphero_table_hit_rate();
```

Both should be above 99%.

## Install

Run this command from your shell:

```sh
curl https://raw.githubusercontent.com/britt/gphero.sql/master/install.sql | psql db_name
```

or [copy its contents](https://raw.githubusercontent.com/britt/gphero.sql/master/install.sql) into a SQL console.

## Uninstall

```sh
curl https://raw.githubusercontent.com/britt/gphero.sql/master/uninstall.sql | psql db_name
```

## Contributing

Everyone is encouraged to help improve this project. Here are a few ways you can help:

- [Report bugs](https://github.com/ankane/pghero.sql/issues)
- Fix bugs and [submit pull requests](https://github.com/ankane/pghero.sql/pulls)
- Write, clarify, or fix documentation
- Suggest or add new features
