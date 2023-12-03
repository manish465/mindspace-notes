The Factory Method Pattern is a [[creational design pattern]]

Defines an interface for creating an object, but leaves the choice of its type to the subclasses, creating an instance of one of several possible classes.

```Java
// Step 1: Product Interface
interface Animal {
    void makeSound();
}

// Step 2: Concrete Products
class Dog implements Animal {
    @Override
    public void makeSound() {
        System.out.println("Dog barks");
    }
}

class Cat implements Animal {
    @Override
    public void makeSound() {
        System.out.println("Cat meows");
    }
}

// Step 3: Creator Interface
interface AnimalFactory {
    Animal createAnimal();
}

// Step 4: Concrete Creators
class DogFactory implements AnimalFactory {
    @Override
    public Animal createAnimal() {
        return new Dog();
    }
}

class CatFactory implements AnimalFactory {
    @Override
    public Animal createAnimal() {
        return new Cat();
    }
}

// Step 5: Client Code
public class Main {
    public static void main(String[] args) {
        AnimalFactory dogFactory = new DogFactory();
        Animal dog = dogFactory.createAnimal();
        dog.makeSound();  // Output: Dog barks

        AnimalFactory catFactory = new CatFactory();
        Animal cat = catFactory.createAnimal();
        cat.makeSound();  // Output: Cat meows
    }
}
```

#design-pattern 