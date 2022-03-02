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
## Liskov Substitution

>  If class A is a subtype of class B, we should be able to replace B with A without disrupting the behavior of our program.  
> A derived class must be replaceable with its base class.

``` java

public class Fruit {
    
    public void getFruitName() {
    
        System.out.println('Fruit');
        
    }
    
}

public class Jackfruit extends Fruit {
    
    public void getFruitName() {
    
        System.out.println('Jackfruit');
        
    }
    
}

public void printFruitName(Fruit fruit) {

    return fruit.getFruitName();
    
}

// printFruitName(Fruit fruit) can receive a Fruit arg and also a Jackfruit arg.

```

## Interface Segregation

>  A class should not be forced to implement interfaces and methods that it will not use, larger interfaces should be split into smaller ones. By doing so, we can ensure that implementing classes only need to be concerned about the methods that are of interest to them.

``` java

public interface Mammals {

    public void getMammaryGlands(){ ... };
    public void pulmonaryBreathing(){ ... };
    
}

public interface EggMammals extends Mammals {
    
    public void getMammaryGlands(){ ... };
    public void pulmonaryBreathing(){ ... };
    public void layEgg(){ ... };
    
}

public class Whale implements Mammals() {
    
    public void getMammaryGlands(){ ... };
    public void pulmonaryBreathing(){ ... };
    
}

public class Platypus implements EggMammals() {
    
    public void getMammaryGlands(){ ... };
    public void pulmonaryBreathing(){ ... };
    public void layEgg(){ ... };
    
}

```

### References:

[A Solid Guide to SOLID Principles](https://www.baeldung.com/solid-principles)  
[O que é SOLID: O guia completo para você entender os 5 princípios da POO](https://medium.com/desenvolvendo-com-paixao/o-que-é-solid-o-guia-completo-para-você-entender-os-5-princípios-da-poo-2b937b3fc530)
