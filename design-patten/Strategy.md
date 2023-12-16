**What is Strategy?**

The Strategy pattern is a behavioral design pattern that lets you dynamically change an algorithm's implementation without modifying the client code that uses it. It achieves this by [[Encapsulation|encapsulating]] different algorithms (strategies) in separate classes, and then allowing the client to choose and inject the desired strategy at runtime.

**Why use Strategy?**

There are several benefits to using Strategy:

- **Flexibility:** You can easily add or remove new algorithms without affecting existing code.
- **Maintainability:** The code becomes more modular and easier to understand and maintain, as the algorithms are separated from the client code.
- **[[Open and Closed Principle|Open/Closed Principle]]:** You can adhere to the Open/Closed Principle by adding new algorithms without modifying existing code.
- **[[Polymorphism]]:** You can achieve polymorphism by treating different strategies as interchangeable implementations of the same interface.

**Where is Strategy used?**

Here are some common examples of where the Strategy pattern is used:

- **Sorting algorithms:** You can choose different sorting algorithms (e.g., bubble sort, merge sort, quicksort) based on the data size or performance requirements.
- **Image compression:** You can use different compression algorithms (e.g., JPEG, PNG) depending on the desired level of compression and image quality.
- **Payment processing:** You can integrate different payment gateways (e.g., PayPal, Stripe) without modifying the core shopping cart functionality.
- **Gaming AI:** You can define different AI behaviors (e.g., aggressive, defensive) for different game characters or situations.

**When to use Strategy?**

Consider using the Strategy pattern when:

- You have multiple algorithms for the same task, and you want to choose between them at runtime.
- You want to avoid tight coupling between the client code and the specific algorithm implementation.
- You need to extend the behavior of existing code without modifying it directly.

**How is Strategy implemented?**

Here's a basic example of how the Strategy pattern can be implemented:

```Java
interface SortStrategy {
  int[] sort(int[] data);
}

class BubbleSortStrategy implements SortStrategy {
  @Override
  public int[] sort(int[] data) {
    // Implement the bubble sort algorithm
    // ...
  }
}

class MergeSortStrategy implements SortStrategy {
  @Override
  public int[] sort(int[] data) {
    // Implement the merge sort algorithm
    // ...
  }
}

class SortingContext {
  private SortStrategy strategy;

  public void setSortingStrategy(SortStrategy strategy) {
    this.strategy = strategy;
  }

  public int[] sort(int[] data) {
    return strategy.sort(data);
  }
}

// Usage
SortingContext context = new SortingContext();
context.setSortingStrategy(new BubbleSortStrategy());
int[] sortedData = context.sort(data);

// Change sorting strategy dynamically
context.setSortingStrategy(new MergeSortStrategy());
sortedData = context.sort(data);
```

This example demonstrates how the `SortingContext` class can use different sorting strategies (`BubbleSortStrategy` and `MergeSortStrategy`) by simply changing the injected instance. This allows the client to choose the desired sorting behavior at runtime without modifying the `SortingContext` code itself.

#design-pattern #behavioral-pattern