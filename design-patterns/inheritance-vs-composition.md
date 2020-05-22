# Inheritance vs Composition

## [Krzysztof Grzybek](https://github.com/krzysztof-grzybek)

It depends on the case. The issue with inheritance is that it breaks encapsulation and creates a tight coupling between the parent class and subclasses.<br/>
We might end up also with a single big class. On the other hand, with the composition, we might end up with a lot of small classes. If the relation between the object is `is a` and we.</br>
want to have slightly different behavior, I would choose inheritance. In other cases, I would choose a composition.
