## Database Crates

Rust has three main options for interacting with PostgreSQL:

- `tokio-postgres`
- `sqlx`
- `diesel`

### How to choose?

Compile-time safety:

`diesel` and `sqlx` both interact with the database at compile-time to detect obvious errors. `diesel` uses Rust's type safety, and `sqlx` can optionally perform validation using macros.

Query Interface:

`tokio-postgres` and `sqlx` expect you to write queries with SQL directly. `diesel` provides its own query builder: queries are defined as Rust types, and you use methods to perform joins and similar operations. This does mean that there are upfront learning costs to using `diesel`, as SQL is very versatile for any project, whereas `diesel`'s DSL (Domain Specific Language) is only useful if you stick to `diesel`. Also, `diesel` can struggle to represent complex queries, so you may end up writing SQL anyway.

Async Support:

`tokio-postgres` and `sqlx` both provide an asynchronous interface, while `diesel` is synchronous by default, but does provide async capabilities via `diesel-async`.
