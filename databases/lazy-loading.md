# Lazy Loading

## [Krzysztof Grzybek](https://github.com/krzysztof-grzybek)

Lazy loading is a pattern in which we delay loading the data until it's actually needed. Lazy loading data from the database is usually achieved by Implementing proper Proxy class.

It might be useful if we have an object which requires a lot of data to be fetched from the database, but probably we don't need all the data in every case. It might reduce object initialization phase and memory usage.

On the other hand, we might end up with a lot of database queries to get small chunks of data, and it might cause performance problems. It's not so hard to do that because lazy loading is a very leaking abstraction.

Another pitfall, probably more important is that we might work with inconsistent data. If we loaded user data first, and then after some time we loaded user orders, we can't be sure that the orders data wasn't modified already by someone else.
