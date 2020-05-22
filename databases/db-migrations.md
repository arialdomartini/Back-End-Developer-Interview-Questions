# DB Migrations

## [Krzysztof Grzybek](https://github.com/krzysztof-grzybek)

The strategy would highly depend on application downtime possibility. If some downtime would be possible, migration would be much easier. I would pay attention especially to:
1. Consistency in data changes after migration has been started (if downtime is not possible).
2. Data types compatibility between different db engines.
3. Database api changes.
4. Security issues (we would transfer a lot of sensitive data through the network).
5. Troublesome potential revert.
