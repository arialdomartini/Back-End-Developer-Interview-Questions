# Why are global and static objects evil? Can you show it with a code example?

## [Krzysztof Grzybek](https://github.com/krzysztof-grzybek)

1. Global and static objects causes implicit dependencies/coupling, thus breaks the idea of encapsulation.
2. It's hard to reason about them - logical scope for understanding behaviour of these objects is expanded to the whole program.
3. It's Hard to mock/stub them.
4. Global objects pollutes the main scope.

Bad:
```javascript
class Player {
    walk() {
        this.x = nextDestination.x;
        this.y = nextDestination.y;
    }
}
```

Good:
```javascript
class Player {
    walk(destination) {
        this.x = destination.x;
        this.y = destination.y;
    }
}
```
