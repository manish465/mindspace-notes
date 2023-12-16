**What is the Composite Pattern?**

The Composite pattern allows you to treat individual objects and groups of objects (compositions) in a uniform way. It creates a tree-like structure where objects can act as leaves or internal nodes. This enables you to perform operations on both individual objects and the entire hierarchy as a whole.

**Why use the Composite Pattern?**

- **Simplify hierarchical data manipulation:** Treat individual objects and groups consistently, making code more concise and easier to maintain.
- **Dynamically build structures:** Create complex structures at runtime by adding and removing objects from the composite hierarchy.
- **Recursive processing:** Perform operations on entire hierarchies through a single method call, simplifying code for tasks like traversal or search.

**When to use the Composite Pattern?**

- **Hierarchical data representation:** When your data naturally forms a tree-like structure, like menus, file systems, or organizational charts.
- **Need for flexible operations:** When you need to perform operations on both individual and grouped objects, or on the entire hierarchy.
- **Avoid code duplication:** If you find yourself writing repetitive code for individual and group operations, the Composite pattern can offer a cleaner solution.

**Where to use the Composite Pattern?**

- **GUI components:** Build complex user interfaces by nesting different components like panels, buttons, and menus.
- **Document processing:** Parse and manipulate structured documents like XML or JSON by treating elements and nodes as composites.
- **File systems:** Implement file system operations like directory traversal or file searching in a uniform way for individual files and folders.

**How to implement the Composite Pattern in Java:**

Here's an example of a Composite Shape interface and its implementations:

**1. Define the Composite interface:**

```Java
public interface Shape {
    void draw();
    double getArea();
}
```

**2. Implement Leaf shapes (e.g., Circle, Square):**

```Java
public class Circle implements Shape {
    private double radius;

    @Override
    public void draw() {
        System.out.println("Drawing circle...");
    }

    @Override
    public double getArea() {
        return Math.PI * radius * radius;
    }
}
```

**3. Implement Composite shape (e.g., Group):**

```Java
public class Group implements Shape {
    private List<Shape> children;

    @Override
    public void draw() {
        for (Shape child : children) {
            child.draw();
        }
    }

    @Override
    public double getArea() {
        double totalArea = 0;
        for (Shape child : children) {
            totalArea += child.getArea();
        }
        return totalArea;
    }

    public void addChild(Shape child) {
        children.add(child);
    }
}
```

**Client usage:**

```Java
Shape group1 = new Group();
group1.addChild(new Circle(5));
group1.addChild(new Square(10));

Shape group2 = new Group();
group2.addChild(new Triangle(3, 4, 5));
group2.addChild(group1);

group2.draw(); // Draws all shapes in the hierarchy
System.out.println("Total area: " + group2.getArea()); // Calculates total area of all shapes
```

This example demonstrates how the Composite pattern allows you to build a hierarchy of shapes and perform operations like drawing and calculating area for both individual shapes and the entire group.

**Remember:**

- Define a common interface for all leaf and composite objects.
- Implement drawing and other operations in both Leaf and Composite classes.
- Use the Composite class to manage child objects and delegate operations to them.

#design-pattern #structural-pattern