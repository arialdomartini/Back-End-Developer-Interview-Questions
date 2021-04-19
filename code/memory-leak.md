# Memory Leak

Reference [Effective Java Tuesday! Don't Leak Object References!](https://dev.to/kylec32/effective-java-tuesday-don-t-leak-object-references-1dd9)

bad
```java
    return elements[--size];
```

References to obsolete objects still exist in the array.

good
```java
    Object poppedObject = elements[--size];
    elements[size] = null;
    return poppedObject;
```