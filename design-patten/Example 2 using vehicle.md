Below has the code for `Vehicle` which returns if the vehicle has engine and number of wheels

```Java
public class Vehicle {  
    public Integer getNumberOfWheels(){  
        return 2;  
    }  
  
    public Boolean hasEngine(){  
        return true;  
    }  
}

public class MotorCycle extends Vehicle{  
}

public class Car extends Vehicle{  
    @Override  
    public Integer getNumberOfWheels() {  
        return 4;  
    }  
}

public class Bicycle extends Vehicle{  
    @Override  
    public Boolean hasEngine() {  
        return null;  
    }  
}

public class Main {  
    public static void main(String[] args) {  
        List<Vehicle> vehicleList = new ArrayList<>();  
  
        vehicleList.add(new MotorCycle());  
        vehicleList.add(new Car());  
  
        for (Vehicle vehicle : vehicleList){  
            System.out.println(vehicle.hasEngine().toString());  
        }  
    }  
}
```

the problem here is that `Bicycle` is `@Override` the `hasEngine()` function and retuning `null`, which make sense in real life but this will break the code throw and Exception in ``Main`` class.

To fix it we can create new class `EngineVehicle` which will inherit `Vehicle` and `MotorCycle` and `Car` will inherit `EngineVehicle` 

```Java
public class Vehicle {  
    public Integer getNumberOfWheels(){  
        return 2;  
    }  
}

public class Bicycle extends Vehicle{  
}

public class EngineVehicle extends Vehicle {  
    public Boolean hasEngine(){  
        return true;  
    }  
}

public class MotorCycle extends EngineVehicle{  
}

public class Car extends EngineVehicle{  
    @Override  
    public Integer getNumberOfWheels() {  
        return 4;  
    }  
}

public class Main {  
    public static void main(String[] args) {  
        List<Vehicle> vehicleList = new ArrayList<>();  
  
        vehicleList.add(new MotorCycle());  
        vehicleList.add(new Car());  
  
        for (Vehicle vehicle : vehicleList){  
            System.out.println(vehicle.getNumberOfWheels().toString());  
        }  
    }  
}
```

Now the code will not break and LSP is satisfied here.

#design-pattern 