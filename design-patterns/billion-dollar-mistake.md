# Billion Dollar Mistake

## [Krzysztof Grzybek](https://github.com/krzysztof-grzybek)

The presence of null and its assignability to any type makes programs error-prone. Since any variable can be "null", we never know when we may want to call e.g. some method on null instead of the real object.

Null object pattern mail lead to silent errors. It may be also tedious in maintenance, because we have to update it often when original class changes. It would be helpful when we really want to apply default behavior for some cases.

Option types are awesome, because they are completely safe. However, they might create some overhead with a lot of additional code.
