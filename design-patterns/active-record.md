# Active Record

## [Krzysztof Grzybek](https://github.com/krzysztof-grzybek)

1. Those objects are hard to test - they are tied to the data layer.
2. This design violates SRP, so it might lead us to huge classes with lots of responsibilities.
4. It's easy to hit the database multiple times (e.g. in foreach loop) because of the leaking abstraction.
