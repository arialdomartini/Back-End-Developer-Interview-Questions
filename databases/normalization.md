# Normalization

## [Krzysztof Grzybek](https://github.com/krzysztof-grzybek)

I think that database denormalization is needed only if we need to improve the performance of our queries, and the other optimizations (indexing, sql views) are not enough.
We need to remember that the cost of database denormalization is to build and maintain tools for keeping our data consistent (e.g. crons).
