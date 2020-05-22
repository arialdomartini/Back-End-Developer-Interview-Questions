# Blue-Green Deployment

## [Krzysztof Grzybek](https://github.com/krzysztof-grzybek)

This is the most tricky part of the Blue-Green Deployment. The common solution for this case is to have an intermediate release, with database schema which will be supported by both previous and the next release.
With this approach, we still have all the benefits of the Blue-Green Deployment, including quick revert. The cost is an overhead with the intermediate release.
