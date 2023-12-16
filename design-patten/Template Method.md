The Template Method design pattern provides a flexible way to define an algorithm's overall structure while allowing subclasses to customize specific steps. It's like a recipe with a core process but optional ingredients and cooking steps.

**What is it?**

Imagine a template for making pizza dough. It defines the basic steps like mixing flour, yeast, water, etc. However, subclasses can customize the recipe by adding different toppings, spices, or even changing the baking time. This way, you have a consistent framework for making pizza dough but with room for individual variations.

**Why use it?**

- **Code reuse:** Define the common steps of an algorithm in one place and reuse it across different subclasses.
- **Customization:** Allow subclasses to override specific steps and implement their own logic without modifying the entire algorithm.
- **Open-closed principle:** The overall structure remains closed for modification, while individual steps remain open for extension.
- **Improved maintainability:** Easier to understand and maintain the code as the algorithm is clearly divided into common and specific parts.

**When to use it?**

- When you have an algorithm with common steps but optional variations.
- When you want to promote code reuse while allowing for customization.
- When you need to ensure the overall structure of an algorithm remains consistent while allowing flexibility in specific details.

**Where to use it?**

- Building graphical user interfaces (GUIs): Define the basic flow of a UI while allowing components to customize their behavior.
- Implementing data processing pipelines: Define the common steps for processing data while allowing different algorithms for specific tasks.
- Creating frameworks and libraries: Provide a general framework with optional hooks for customization by users.

**How to implement it?**

2. **Define an abstract class or interface:** This defines the overall algorithm structure and provides abstract methods for the customizable steps.
4. **Implement the common steps in the base class:** These are the steps that are invariant across all subclasses.
6. **Define abstract methods for the customizable steps:** These methods are implemented by subclasses to provide their own logic.
8. **Implement the template method in the base class:** This method calls the common steps and the abstract methods in a specific order to execute the entire algorithm.
10. **Implement the abstract methods in subclasses:** Subclasses override these methods to provide their own implementation for the customizable steps.

**Java Example:**

```Java
abstract class FileProcessor {
    public void processFile(String filename) {
        openFile(filename);
        processLines();
        closeFile();
    }

    abstract void openFile(String filename);
    abstract void processLines();
    abstract void closeFile();
}

class TextFileProcessor extends FileProcessor {
    @Override
    void openFile(String filename) {
        // Open text file
    }

    @Override
    void processLines() {
        // Read and process lines from the text file
    }

    @Override
    void closeFile() {
        // Close the text file
    }
}

class ImageFileProcessor extends FileProcessor {
    @Override
    void openFile(String filename) {
        // Open image file
    }

    @Override
    void processLines() {
        // Extract and process data from the image file
    }

    @Override
    void closeFile() {
        // Close the image file
    }
}
```

This example shows how the Template Method pattern can be used to create different file processors with a common structure but different implementations for opening, processing, and closing files.

**Remember:**

- Clearly define the common and customizable parts of the algorithm.
- Use abstract classes or interfaces to represent the overall structure.
- Provide clear documentation for abstract methods and their expected behavior.
- Use the template method to execute the algorithm with the defined structure.

#design-pattern #behavioral-pattern