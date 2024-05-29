import java.util.Scanner;

abstract class Vehicle {
    private String vehicleNumber;
    
    private String vehicleType;
    
    private String manufacturer;
    
    private int year;

    public Vehicle(String vehicleNumber, String vehicleType, String manufacturer, int year) 
    {
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

    public Motorcycle(String vehicleNumber, String vehicleType, String manufacturer, int year, int engineCapacity, String fuelType) 
    {
        super(vehicleNumber, vehicleType, manufacturer, year);
        
        this.engineCapacity = engineCapacity;
        
        this.fuelType = fuelType;
    }

    @Override
    public void startEngine() 
    {
        System.out.println("Motorcycle engine started");
    }

    public void kickStart() 
    {
        System.out.println("Motorcycle kick started");
    }

    public void displayMotorcycleInfo()
    {
        System.out.println("Engine Capacity: " + engineCapacity + ", Fuel Type: " + fuelType);
    }
}

class Bus extends Vehicle 
{
    private int numSeats;
    private String airConditioningType;

    public Bus(String vehicleNumber, String vehicleType, String manufacturer, int year, int numSeats, String airConditioningType) 
    {
        super(vehicleNumber, vehicleType, manufacturer, year);
        
        this.numSeats = numSeats;
        
        this.airConditioningType = airConditioningType;
    }

    @Override
    public void startEngine()
    {
        System.out.println("Bus engine started");
    }

    public void openDoors()
    {
        System.out.println("Bus doors opened");
    }

    public void displayBusInfo()
    {
        System.out.println("Number of seats: " + numSeats + ", Air Conditioning Type: " + airConditioningType);
    }
}

public class VehicleManagementSystem
{
    public static void main(String[] args)
    {
        Scanner scanner = new Scanner(System.in);

        System.out.println("Enter details for a Car:");
        
        System.out.print("Vehicle Number: ");
        
        String carNumber = scanner.nextLine();
        
        System.out.print("Vehicle Type: ");
        
        String carType = scanner.nextLine();
        
        System.out.print("Manufacturer: ");
        
        String carManufacturer = scanner.nextLine();
        
        System.out.print("Year: ");
        
        int carYear = scanner.nextInt();
        
        System.out.print("Number of Doors: ");
        
        int carDoors = scanner.nextInt();
        
        scanner.nextLine();  
        
        System.out.print("Transmission Type: ");
        
        String carTransmission = scanner.nextLine();

        System.out.println("Enter details for a Motorcycle:");
        
        System.out.print("Vehicle Number: ");
        
        String motorcycleNumber = scanner.nextLine();
        
        System.out.print("Vehicle Type: ");
        
        String motorcycleType = scanner.nextLine();
        
        System.out.print("Manufacturer: ");
        
        String motorcycleManufacturer = scanner.nextLine();
        
        System.out.print("Year: ");
        
        int motorcycleYear = scanner.nextInt();
        
        System.out.print("Engine Capacity: ");
        
        int motorcycleEngine = scanner.nextInt();
        
        scanner.nextLine();  
        
        System.out.print("Fuel Type: ");
        
        String motorcycleFuel = scanner.nextLine();

        System.out.println("Enter details for a Bus:");
        
        System.out.print("Vehicle Number: ");
        
        String busNumber = scanner.nextLine();
        
        System.out.print("Vehicle Type: ");
        
        String busType = scanner.nextLine();
        
        System.out.print("Manufacturer: ");
        
        String busManufacturer = scanner.nextLine();
        
        System.out.print("Year: ");
        
        int busYear = scanner.nextInt();
        
        System.out.print("Number of Seats: ");
        
        int busSeats = scanner.nextInt();
        
        scanner.nextLine();  
        
        System.out.print("Air Conditioning Type: ");
        
        String busAC = scanner.nextLine();

        Vehicle car = new Car(carNumber, carType, carManufacturer, carYear, carDoors, carTransmission);
        
        Vehicle motorcycle = new Motorcycle(motorcycleNumber, motorcycleType, motorcycleManufacturer, motorcycleYear, motorcycleEngine, motorcycleFuel);
        
        Vehicle bus = new Bus(busNumber, busType, busManufacturer, busYear, busSeats, busAC);

        car.startEngine();
        
        car.displayInfo();
        
        if (car instanceof Car) 
        {
            Car c = (Car) car;
            c.displayCarInfo();
        }

        motorcycle.startEngine();
        
        motorcycle.displayInfo();
        
        if (motorcycle instanceof Motorcycle) 
        {
            Motorcycle m = (Motorcycle) motorcycle;
            
            m.displayMotorcycleInfo();
        }

        bus.startEngine();
        
        bus.displayInfo();
        
        if (bus instanceof Bus)
        {
            Bus b = (Bus) bus;
            
            b.displayBusInfo();
        }
    }
}
