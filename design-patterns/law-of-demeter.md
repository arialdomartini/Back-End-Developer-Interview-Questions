# Law of Demeter

## [Krzysztof Grzybek](https://github.com/krzysztof-grzybek)


Code violating The Law of Demeter:
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

