# N + 1 problem

## [Krzysztof Grzybek](https://github.com/krzysztof-grzybek)

It depends on the ORM engine, but generally, the fix is to use `JOIN` query. In hibernate it's e.g. `join fetch` which results in `INNER JOIN` SQL query.
