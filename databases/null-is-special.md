# NULL is special

## [Krzysztof Grzybek](https://github.com/krzysztof-grzybek)

"NULL", basically means "a missing unknown value". It requires often special treatment because it represents something that doesn't exist.
The example above doesn't work, because the result of any arithmetic comparison with NULL is NULL itself, e.g.:

```sql
1 = NULL, 1 <> NULL, 1 < NULL, 1 > NULL
```
, and even
```sql
NULL = NULL
```
It somehow makes sense, because how would you compare a number to something that doesn't exist, or how would you compare something that doesn't exist to something that doesn't exist?!
