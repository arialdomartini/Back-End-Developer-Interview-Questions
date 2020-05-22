# Schema Migrations

## [Krzysztof Grzybek](https://github.com/krzysztof-grzybek)

I would use migration scripts which would be tracked in the version control system. Each change to database schema would be a script ordered chronologically, e.g. they would be named `1_add_age_to_user`, `2_add_price_to_order`.<br/>
I would also track in database which migration scripts were executed already. With setup like this, it would be easy to execute migration scripts automatically - in development environment on application start, and in CI - before deployment. 
