Suppose you have a system that handles various shapes, such as circles, rectangles, and triangles. You initially implement an area calculation method like this:

```Java
class Circle {
    double radius;
    
    public Circle(double radius) {
        this.radius = radius;
    }
    
    public double calculateArea() {
        return Math.PI * radius * radius;
    }
}

class Rectangle {
    double width;
    double height;
    
    public Rectangle(double width, double height) {
        this.width = width;
        this.height = height;
    }
    
    public double calculateArea() {
        return width * height;
    }
}
```

At some point, you decide to add support for calculating the area of triangles. In a non-Open/Closed design, you might modify the existing classes to include the new functionality. However, this violates the Open/Closed Principle because you are modifying existing code.

To adhere to the Open/Closed Principle, you would create an interface or an abstract class representing the shape, and then create new classes that implement this interface to handle different shapes. You can also use a strategy pattern or dependency injection to extend the functionality without modifying the existing code:

```Java
interface Shape {
    double calculateArea();
}

class Circle implements Shape {
    double radius;

    public Circle(double radius) {
        this.radius = radius;
    }

    public double calculateArea() {
        return Math.PI * radius * radius;
    }
}

class Rectangle implements Shape {
    double width;
    double height;

    public Rectangle(double width, double height) {
        this.width = width;
        this.height = height;
    }

    public double calculateArea() {
        return width * height;
    }
}

class Triangle implements Shape {
    double base;
    double height;

    public Triangle(double base, double height) {
        this.base = base;
        this.height = height;
    }

    public double calculateArea() {
        return 0.5 * base * height;
    }
}
```

With this design, you can add new shape classes without modifying the existing ones, thus adhering to the Open/Closed Principle. This approach makes it easier to extend the system's functionality and maintain the code.

#design-pattern 