**What is the Decorator?**

The Decorator pattern provides a flexible way to add new behaviors to objects without modifying their original structure. It achieves this by:

- **Wrapping the original object:** The decorator class wraps the object you want to decorate and adds its own functionality to it.
- **Implementing the same interface:** Both the decorated object and the decorator class implement the same interface, ensuring seamless integration with the client code.
- **Delegating functionality:** The decorator typically delegates basic functionality to the decorated object and adds its own behavior before or after the delegated call.
- **Stacking decorators:** You can chain multiple decorators together to add multiple functionalities in a layered fashion.

**Why use the Decorator?**

There are several benefits to using the Decorator pattern:

- **Flexibility:** You can easily add new functionalities to existing objects without modifying their original code.
- **Open/Closed Principle:** You can extend the behavior of objects without modifying their existing interfaces.
- **Loose coupling:** The client code is only coupled to the common interface, not the specific implementations of the decorated objects.
- **Undo/redo functionality:** You can easily remove or reorder decorators to change the object's behavior at runtime.

**Where is the Decorator used?**

Here are some common examples of where the Decorator pattern is used:

- **GUI components:** Adding borders, scrollbars, or other visual enhancements to existing UI elements like buttons or text fields.
- **Logging:** Adding timestamps, formatting, or filtering functionalities to existing logging systems.
- **Data processing:** Applying compression, encryption, or other transformations to data streams or files before processing.
- **Networking:** Adding authentication, encryption, or caching functionalities to network communication channels.

**When to use the Decorator?**

Consider using the Decorator pattern when:

- You need to dynamically add functionalities to existing objects.
- You want to avoid modifying the original code of the decorated objects.
- You want to be able to stack multiple functionalities on top of each other.
- You need a flexible and open-ended approach to adding new behaviors.

**How is the Decorator implemented?**

Here's a basic example of how the Decorator pattern can be implemented in Java:

```Java
interface Logger {
  void log(String message);
}

class FileLogger implements Logger {
  @Override
  public void log(String message) {
    // Write message to a file
  }
}

class TimestampDecorator implements Logger {
  private Logger decoratedLogger;

  public TimestampDecorator(Logger decoratedLogger) {
    this.decoratedLogger = decoratedLogger;
  }

  @Override
  public void log(String message) {
    decoratedLogger.log(String.format("[%s] %s", LocalDateTime.now(), message));
  }
}

// Usage
Logger logger = new TimestampDecorator(new FileLogger());
logger.log("This message is logged with a timestamp.");
```

This example demonstrates a `TimestampDecorator` that wraps a `FileLogger` and adds the functionality of prepending a timestamp to the logged message. You can easily chain multiple decorators to add more functionalities like encryption or filtering before writing to the file.

#design-pattern #structural-pattern