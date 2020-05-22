# Tell me about Inversion of Control and how it improves the design of code

## [Krzysztof Grzybek](https://github.com/krzysztof-grzybek)

Inversion of Control is a pattern in which we reverse the relation of the code execution: we don't call the external code, external code calls our code.
E.g. when working we libraries, we usually import some module and call functions from that module. When working with frameworks, our custom code 
is called by the framework code. This is also known as the Hollywood Principle - "Don't call us, we'll call you".
It may help keeping single responsibility of the specific classes and design more concise API's.
