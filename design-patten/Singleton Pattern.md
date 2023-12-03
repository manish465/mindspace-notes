The Singleton Pattern is a [[creational design pattern]] that ensures a class has only one instance and provides a global point of access to that instance. 

It is often used when exactly one object is needed to coordinate actions across the system, such as a configuration manager, logging service, or database connection pool.

```Java
public class Singleton {

    // Step 1: Private static instance
    private static Singleton instance;

    // Step 2: Private constructor to prevent instantiation
    private Singleton() {
        // Initialization code, if any
    }

    // Step 3: Public static method to access the instance
    public static Singleton getInstance() {
        if (instance == null) {
            // Lazy initialization: create the instance only when needed
            instance = new Singleton();
        }
        return instance;
    }

    // Other methods and properties of the singleton class
    public void doSomething() {
        System.out.println("Singleton is doing something.");
    }
}

public class Main {
    public static void main(String[] args) {
        // Access the singleton instance
        Singleton singleton1 = Singleton.getInstance();
        Singleton singleton2 = Singleton.getInstance();

        // Both references point to the same instance
        System.out.println(singleton1 == singleton2);  // Output: true

        // Call methods on the singleton instance
        singleton1.doSomething();
    }
}
```

#design-pattern 