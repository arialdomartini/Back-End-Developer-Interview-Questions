# Law of Demeter

* [Law of Demeter - Wikipedia](https://en.wikipedia.org/wiki/Law_of_Demeter)
* [Law of Demeter - WikiWikiWeb](https://wiki.c2.com/?LawOfDemeter)
* [Introducing Demeter and its Laws](http://www.bradapp.net/docs/demeter-intro.html)

## Mnemonic for the Law of Demeter
The post [Visualization Mnemonics for Software Principles](http://www.daedtech.com/visualization-mnemonics-for-software-principles) by [Erik Dietrich](https://github.com/erikdietrich) provides a very effective trick to understand (and never forget anymore) what the Law of Demeter is. An Italian translation is available [here](https://github.com/arialdomartini/mnemonics/blob/law-of-demeter/README-italian.md).

## Code Example
An example of code violating the Law of Demeter is provided by [Krzysztof Grzybek](https://github.com/krzysztof-grzybek)

```javascript
class Plane {
    constructor(crew) {
        this.crew = crew;
    }
    
    getPilotsName() {
        this.crew.pilot.getName();
    }
}

class Crew {
    constructor(pilot) {
        this.pilot = pilot;
    }
}

class Pilot {
    getName() {
        // ...
    }
}
```

It's bad, because it creates tight coupling between objects - they are dependent on internal structure of other objects.

Fixed code:
```javascript
class Plane {
    getPilotsName() {
        this.crew.getPilotsName();
    }
}

class Crew {
    constructor(pilot) {
        this.pilot = pilot;
    }

    getPilotsName() {
        return this.pilot.getName();
    }
}
