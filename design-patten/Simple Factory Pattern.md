Provides a class that has one creation method with a large conditional that based on method parameters chooses which product class to instantiate and then return.

```
// Step 1: Product (Shape) Interface
interface Shape {
    void draw();
}

// Step 2: Concrete Products (Circle, Rectangle)
class Circle implements Shape {
    @Override
    public void draw() {
        System.out.println("Drawing a Circle");
    }
}

class Rectangle implements Shape {
    @Override
    public void draw() {
        System.out.println("Drawing a Rectangle");
    }
}

// Step 3: Factory (ShapeFactory)
class ShapeFactory {
    public Shape createShape(String shapeType) {
        if (shapeType.equalsIgnoreCase("circle")) {
            return new Circle();
        } else if (shapeType.equalsIgnoreCase("rectangle")) {
            return new Rectangle();
        } else {
            throw new IllegalArgumentException("Invalid shape type");
        }
    }
}

// Step 4: Client Code
public class Main {
    public static void main(String[] args) {
        ShapeFactory shapeFactory = new ShapeFactory();

        // Creating a circle
        Shape circle = shapeFactory.createShape("circle");
        circle.draw();  // Output: Drawing a Circle

        // Creating a rectangle
        Shape rectangle = shapeFactory.createShape("rectangle");
        rectangle.draw();  // Output: Drawing a Rectangle
    }
}
```

#design-pattern 