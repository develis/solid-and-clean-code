# SOLID
> Martin and Feathers' design principles encourage us to create more maintainable, understandable, and flexible software. Consequently, as our applications grow in size, we can reduce their complexity and save ourselves a lot of headaches further down the road.

- **S O L I D**
- Single Responsibility
- Open/Closed
- Liskov Substitution
- Interface Segregation
- Dependency Inversion

## Single Responsibility

> A class must have one, and only one, reason to change.

``` java
abstract class Employee {
    
    private String name;
    
}

public class Driver extends Employee {

    private String driverLicense;
    
    //constructor, getters and setters...
    
    public void drive() { ... }
    
}

public class Chef extends Employee {

    private String chefSpecialDish;
    
    //constructor, getters and setters...
    
    public void cook() { ... }
    
}
```

## Open/Closed

> Classes should be open for extension but closed for modification.
> Separate extensible behavior behind an interface, and flip the dependencies.

``` java

public interface Wage {
    
    public double calculateWages();
    
}

public class HourlyPay implements Wage {

    public double calculateWages() { ... };
    
}

public class MonthlyPay implements Wage {

    public double calculateWages() { ... };
    
}

```

### References:

[A Solid Guide to SOLID Principles](https://www.baeldung.com/solid-principles)
[O que é SOLID: O guia completo para você entender os 5 princípios da POO](https://medium.com/desenvolvendo-com-paixao/o-que-é-solid-o-guia-completo-para-você-entender-os-5-princípios-da-poo-2b937b3fc530)
