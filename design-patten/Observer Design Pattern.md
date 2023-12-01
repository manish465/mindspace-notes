The Observer Design Pattern is a [[behavioral design patten]] where an object, known as the subject, maintain a list of its dependents, called observers, that are notified of any changes in the subjects state. This patten is useful when you have a one to may relationship between objects, and you want to notify multiple objects about changes without coupling them tightly.

```
import java.util.ArrayList;
import java.util.List;

// Step 1: Define the Observer interface
interface Observer {
    void update(String message);
}

// Step 2: Create Concrete Observer
class ConcreteObserver implements Observer {
    private String name;

    public ConcreteObserver(String name) {
        this.name = name;
    }

    @Override
    public void update(String message) {
        System.out.println(name + " received message: " + message);
    }
}

// Step 3: Define the Subject interface
interface Subject {
    void addObserver(Observer observer);
    void removeObserver(Observer observer);
    void notifyObservers(String message);
}

// Step 4: Create Concrete Subject
class ConcreteSubject implements Subject {
    private List<Observer> observers = new ArrayList<>();
    private String state;

    public void setState(String state) {
        this.state = state;
        notifyObservers("State updated: " + state);
    }

    @Override
    public void addObserver(Observer observer) {
        observers.add(observer);
    }

    @Override
    public void removeObserver(Observer observer) {
        observers.remove(observer);
    }

    @Override
    public void notifyObservers(String message) {
        for (Observer observer : observers) {
            observer.update(message);
        }
    }
}

// Step 5: Client Code
public class Main {
    public static void main(String[] args) {
        ConcreteSubject subject = new ConcreteSubject();

        // Create observers
        Observer observer1 = new ConcreteObserver("Observer 1");
        Observer observer2 = new ConcreteObserver("Observer 2");

        // Attach observers to the subject
        subject.addObserver(observer1);
        subject.addObserver(observer2);

        // Change the state of the subject
        subject.setState("New State");

        // Detach an observer
        subject.removeObserver(observer1);

        // Change the state again
        subject.setState("Another State");
    }
}
```

In the above example:
- The `Observer` interface declares the `update` method that concrete observers will implement to receive updates.
- `ConcreteObserver` is a concrete observer class that implements the `Observer` interface.
- The `Subject` interface declares methods for managing observers (`addObserver`, `removeObserver`) and notifying them (`notifyObservers`).
- `ConcreteSubject` is a concrete subject class that implements the `Subject` interface. It maintains a list of observers, notifies them when its state changes, and allows observers to be added or removed.
- In the client code, observers are created and attached to the subject. When the state of the subject changes, all attached observers are notified.

#design-pattern 