```Java
class Bird {
    void fly() {
        System.out.println("Bird is flying.");
    }
}

class Penguin extends Bird {
    // Penguins cannot fly, so they override the fly method.
    @Override
    void fly() {
        System.out.println("Penguin cannot fly.");
    }
}
```

In this example, `Penguin` is a subtype of `Bird`, and it correctly overrides the `fly` method to indicate that penguins cannot fly. The behavior of the derived class does not weaken or violate the expectations of the base class. You can substitute a `Penguin` object for a `Bird` object, and the program's correctness is preserved.

Adhering to the Liskov Substitution Principle leads to more robust and maintainable object-oriented code by ensuring that inheritance hierarchies respect the expected behavior and contracts. It helps prevent subtle bugs and surprises when using derived classes in place of their base classes.

#design-pattern 