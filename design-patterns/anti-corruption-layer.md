# What is an Anti-corruption Layer?
  
## [Krzysztof Grzybek](https://github.com/krzysztof-grzybek)

It's a layer in the system which is responsible for communication between subsystems (most likely with the external or legacy system) which don't operate on the same models.
Its purpose is to create an isolating layer which provides clients with functionality in terms of their own domain model.
