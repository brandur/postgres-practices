# Postgres Practices

Postgres Practices is intended to be a succinct guide to
practical best practices to keep in mind while using and
operating Postgres, as well as when building software on
it. The official [user manual][manual] is an exhaustive
resource to act as a canonical reference most of the time,
but it tends to be _so_ comprehensive that it's easy to
miss some useful advice amongst its sea of information.

## Designing Postgres schemas

### Constraints

#### Use non-nullable by default

#### Foreign keys and `RESTRICT`

#### Put maximum lengths on text

Increasing length of a `VARCHAR` is free.

#### Add `CHECK` constraints

`CHECK (price > 0)`
`CHECK (char_length(name) <= 255)`

#### Specify `UNIQUE` as appropriate

### Types

#### Use a descriptive type

IP as `CIDR`

Longitude and latitude as `NUMERIC(10, 13)

#### Prefer `BIGINT` and `BIGSERIAL`

#### `TEXT` versus `VARCHAR`

#### Prefer `JSONB` for schemaless data

Over `HSTORE` and `JSON`.

### Indexes

#### Use B-trees

#### Create and drop `CONCURRENTLY`

#### Use partial indexes where possible

#### Multi-column indexes cover left fields

> A multicolumn B-tree index can be used with query conditions that involve any subset of the index's columns, but the index is most efficient when there are constraints on the leading (leftmost) columns.

## Building applications on Postgres

### Architecture

#### Build with transactions

#### Manage connections

### Configuration

#### Set application names

#### Set statement timeouts

## Operating Postgres

### Known major operational problems

#### Bloat

#### Large tables

Use partitioning.

#### Full table locks

### Introspection

#### `pg_stat_activity`

### Tooling

#### Learn psql

[manual]: https://
