Public abstract class Vehicle {
    Private String vehicleNumber;
    Private String vehicleType;
    Private String manufacturer;
    Private int year;

    Public Vehicle(String vehicleNumber, String vehicleType, String manufacturer, int year) {
        This.vehicleNumber = vehicleNumber;
        This.vehicleType = vehicleType;
        This.manufacturer = manufacturer;
        This.year = year;
    }

    Public abstract void startEngine();

    Public void displayInfo() {
        System.out.println(“Vehicle Number: “ + vehicleNumber + “, Vehicle Type: “ + vehicleType + “, Manufacturer: “ + manufacturer + “, Year: “ + year);
    }
}
Public class Car extends Vehicle {
    Private int numDoors;
    Private String transmissionType;

    Public Car(String vehicleNumber, String vehicleType, String manufacturer, int year, int numDoors, String transmissionType) {
        Super(vehicleNumber, vehicleType, manufacturer, year);
        This.numDoors = numDoors;
        This.transmissionType = transmissionType;
    }

    @Override
    Public void startEngine() {
        System.out.println(“Car engine started”);
    }

    Public void openDoors() {
        System.out.println(“Car doors opened”);
    }

    Public void displayCarInfo() {
        System.out.println(“Number of doors: “ + numDoors + “, Transmission Type: “ + transmissionType);
    }
}
Public class Motorcycle extends Vehicle {
    Private int engineCapacity;
    Private String fuelType;

    Public Motorcycle(String vehicleNumber, String vehicleType, String manufacturer, int year, int engineCapacity, String fuelType) {
        Super(vehicleNumber, vehicleType, manufacturer, year);
        This.engineCapacity = engineCapacity;
        This.fuelType = fuelType;
    }

    @Override
    Public void startEngine() {
        System.out.println(“Motorcycle engine started”);
    }

    Public void kickStart() {
        System.out.println(“Motorcycle kick started”);
    }

    Public void displayMotorcycleInfo() {
        System.out.println(“Engine Capacity: “ + engineCapacity + “, Fuel Type: “ + fuelType);
    }
}
Public class Bus extends Vehicle {
    Private int numSeats;
    Private String airConditioningType;

    Public Bus(String vehicleNumber, String vehicleType, String manufacturer, int year, int numSeats, String airConditioningType) {
        Super(vehicleNumber, vehicleType, manufacturer, year);
        This.numSeats = numSeats;
        This.airConditioningType = airConditioningType;
    }

    @Override
    Public void startEngine() {
        System.out.println(“Bus engine started”);
    }

    Public void openDoors() {
        System.out.println(“Bus doors opened”);
    }

    Public void displayBusInfo() {
        System.out.println(“Number of seats: “ + numSeats + “, Air Conditioning Type: “ + airConditioningType);
    }
}

Public class VehicleManagementSystem {
    Public static void main(String[] args) {
        Vehicle car = new Car(“KA01AB1234”, “Sedan”, “Toyota”, 2020, 4, “Automatic”);
        Vehicle motorcycle = new Motorcycle(“KA01AB5678”, “Sport”, “Honda”, 2018, 500, “Petrol”);
        Vehicle bus = new Bus(“KA01AB9012”, “City Bus”, “Tata”, 2015, 50, “Manual”);

        Car.startEngine();
        Car.displayInfo();
        If (car instanceof Car) {
            Car c = (Car) car;
            c.displayCarInfo();
        }

        Motorcycle.startEngine();
        Motorcycle.displayInfo();
        If (motorcycle instanceof Motorcycle) {
            Motorcycle m = (Motorcycle) motorcycle;
            m.displayMotorcycleInfo();
        }

        Bus.startEngine();
        Bus.displayInfo();
        If (bus instanceof Bus) {
            Bus b = (Bus) bus;
            b.displayBusInfo();
        }
    }
}
