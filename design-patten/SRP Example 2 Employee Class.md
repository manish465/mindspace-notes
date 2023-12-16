Here's an example with an `Employee` class in Java:

```Java
public class Employee {
    private String name;
    private int employeeId;
    private double salary;
    private List<String> benefits;

    public Employee(String name, int employeeId) {
        this.name = name;
        this.employeeId = employeeId;
        this.salary = 0;
        this.benefits = new ArrayList<>();
    }

    public void calculateSalary() {
        // Code to calculate the employee's salary
    }

    public void manageBenefits(List<String> benefits) {
        // Code to manage employee benefits
    }
}
```

To adhere to the [[Single Responsibility Principle|SRP]], we can separate responsibilities into distinct classes:

```Java
public class Employee {
    private String name;
    private int employeeId;
    private double salary;

    public Employee(String name, int employeeId) {
        this.name = name;
        this.employeeId = employeeId;
        this.salary = 0;
    }
}

public class SalaryCalculator {
    public void calculateSalary(Employee employee) {
        // Code to calculate the employee's salary
    }
}

public class BenefitsManager {
    public void manageBenefits(Employee employee, List<String> benefits) {
        // Code to manage employee benefits
    }
}
```

With this separation, each class has a single responsibility, improving code maintainability and reducing the risk of errors when changes are made.

#design-pattern #SOLID 