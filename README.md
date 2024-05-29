 abstract class Vehicle {
    private String vehicleNumber;
    private String vehicleType;
    private String manufacturer;
    private int year;

    public Vehicle(String vehicleNumber, String vehicleType, String manufacturer, int year) {
        this.vehicleNumber = vehicleNumber;
        this.vehicleType = vehicleType;
        this.manufacturer = manufacturer;
        this.year = year;
    }

    public abstract void startEngine();

    public void displayInfo() {
        System.out.println("Vehicle Number: " + vehicleNumber + ", Vehicle Type: " + vehicleType + ", Manufacturer: " + manufacturer + ", Year: " + year);
    }
}

class Car extends Vehicle {
    private int numDoors;
    private String transmissionType;

    public Car(String vehicleNumber, String vehicleType, String manufacturer, int year, int numDoors, String transmissionType) {
        super(vehicleNumber, vehicleType, manufacturer, year);
        this.numDoors = numDoors;
        this.transmissionType = transmissionType;
    }

    @Override
    public void startEngine() {
        System.out.println("Car engine started");
    }

    public void openDoors() {
        System.out.println("Car doors opened");
    }

    public void displayCarInfo() {
        System.out.println("Number of doors: " + numDoors + ", Transmission Type: " + transmissionType);
    }
}

 class Motorcycle extends Vehicle {
    private int engineCapacity;
    private String fuelType;

    public Motorcycle(String vehicleNumber, String vehicleType, String manufacturer, int year, int engineCapacity, String fuelType) {
        super(vehicleNumber, vehicleType, manufacturer, year);
        this.engineCapacity = engineCapacity;
        this.fuelType = fuelType;
    }

    @Override
    public void startEngine() {
        System.out.println("Motorcycle engine started");
    }

    public void kickStart() {
        System.out.println("Motorcycle kick started");
    }

    public void displayMotorcycleInfo() {
        System.out.println("Engine Capacity: " + engineCapacity + ", Fuel Type: " + fuelType);
    }
}

 class Bus extends Vehicle {
    private int numSeats;
    private String airConditioningType;

    public Bus(String vehicleNumber, String vehicleType, String manufacturer, int year, int numSeats, String airConditioningType) {
        super(vehicleNumber, vehicleType, manufacturer, year);
        this.numSeats = numSeats;
        this.airConditioningType = airConditioningType;
    }

    @Override
    public void startEngine() {
        System.out.println("Bus engine started");
    }

    public void openDoors() {
        System.out.println("Bus doors opened");
    }

    public void displayBusInfo() {
        System.out.println("Number of seats: " + numSeats + ", Air Conditioning Type: " + airConditioningType);
    }
}

public class VehicleManagementSystem {
    public static void main(String[] args) {
        Vehicle car = new Car("KA01AB1234", "Sedan", "Toyota", 2020, 4, "Automatic");
        Vehicle motorcycle = new Motorcycle("KA01AB5678", "Sport", "Honda", 2018, 500, "Petrol");
        Vehicle bus = new Bus("KA01AB9012", "City Bus", "Tata", 2015, 50, "Manual");

        car.startEngine();
        car.displayInfo();
        if (car instanceof Car) {
            Car c = (Car) car;
            c.displayCarInfo();
        }

        motorcycle.startEngine();
        motorcycle.displayInfo();
        if (motorcycle instanceof Motorcycle) {
            Motorcycle m = (Motorcycle) motorcycle;
            m.displayMotorcycleInfo();
        }

        bus.startEngine();
        bus.displayInfo();
        if (bus instanceof Bus) {
            Bus b = (Bus) bus;
            b.displayBusInfo();
        }
    }
}
