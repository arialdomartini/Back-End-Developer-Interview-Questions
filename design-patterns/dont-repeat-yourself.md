# Don't Repeat Yourself

## [Krzysztof Grzybek](https://github.com/krzysztof-grzybek)

Code violating the DRY principle:
```javascript
class Employee {
    calculateSalaryNet() {
        return this.hoursWorked * this.hourlyWage;
    }

    calculateSalaryGross() {
        return this.hoursWorked * this.hourlyWage + TAX;
    }
}
```

Fixed code:
```javascript
class Employee {
    calculateSalaryNet() {
        return this.hoursWorked * this.hourlyWage;
    }

    calculateSalaryGross() {
        return this.calculateSalaryNet() + TAX;
    }
}
```
