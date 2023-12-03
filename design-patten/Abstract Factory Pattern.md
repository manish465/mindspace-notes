The Abstract Factory Pattern is a [[creational design pattern]]

Provides an interface for creating families of related or dependent objects without specifying their concrete classes. It is an extension of the [[Factory Method Pattern]], where a family of related or dependent products is created without specifying their concrete classes.

```Java
// Step 1: AbstractProduct Interfaces (Shape, Color)
interface Shape {
    void draw();
}

interface Color {
    void fill();
}

// Step 2: ConcreteProduct Classes (Circle, Square, Red, Blue)
class Circle implements Shape {
    @Override
    public void draw() {
        System.out.println("Drawing a Circle");
    }
}

class Square implements Shape {
    @Override
    public void draw() {
        System.out.println("Drawing a Square");
    }
}

class Red implements Color {
    @Override
    public void fill() {
        System.out.println("Filling with Red color");
    }
}

class Blue implements Color {
    @Override
    public void fill() {
        System.out.println("Filling with Blue color");
    }
}

// Step 3: AbstractFactory Interface
interface AbstractFactory {
    Shape createShape();
    Color createColor();
}

// Step 4: ConcreteFactory Classes (ShapeFactory, ColorFactory)
class ShapeFactory implements AbstractFactory {
    @Override
    public Shape createShape() {
        return new Circle();
    }

    @Override
    public Color createColor() {
        return new Red();
    }
}

class ColorFactory implements AbstractFactory {
    @Override
    public Shape createShape() {
        return new Square();
    }

    @Override
    public Color createColor() {
        return new Blue();
    }
}

// Step 5: Client Code
public class Main {
    public static void main(String[] args) {
        // Create a shape factory
        AbstractFactory shapeFactory = new ShapeFactory();

        // Create a circle and a red color using the shape factory
        Shape circle = shapeFactory.createShape();
        Color red = shapeFactory.createColor();

        circle.draw();  // Output: Drawing a Circle
        red.fill();     // Output: Filling with Red color

        // Create a color factory
        AbstractFactory colorFactory = new ColorFactory();

        // Create a square and a blue color using the color factory
        Shape square = colorFactory.createShape();
        Color blue = colorFactory.createColor();

        square.draw();  // Output: Drawing a Square
        blue.fill();    // Output: Filling with Blue color
    }
}
```


#design-pattern 