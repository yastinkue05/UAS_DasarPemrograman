import java.util.ArrayList;
import java.util.InputMismatchException;
import java.util.List;
import java.util.Scanner;

class Car {
    private String carId;
    private String modelName;
    private int year;
    private double price;

    public Car(String carId, String modelName, int year, double price) {
        this.carId = carId;
        this.modelName = modelName;
        this.year = year;
        this.price = price;
    }

    // Getters and Setters

    public String toString() {
        return "Car ID: " + carId + ", Model: " + modelName + ", Year: " + year + ", Price: $" + price;
    }

    public String getCarId() {
        return carId;
    }

    public void setCarId(String carId) {
        this.carId = carId;
    }

    public String getModelName() {
        return modelName;
    }

    public void setModelName(String modelName) {
        this.modelName = modelName;
    }

    public int getYear() {
        return year;
    }

    public void setYear(int year) {
        this.year = year;
    }

    public double getPrice() {
        return price;
    }

    public void setPrice(double price) {
        this.price = price;
    }
}

class CarDealership {
    private List<Car> cars;

    public CarDealership() {
        this.cars = new ArrayList<>();
    }

    public void addCar(Car car) {
        cars.add(car);
    }

    public void displayCars() {
        for (Car car : cars) {
            System.out.println(car);
        }
    }

    public void updateCar(String carId, String newModelName, int newYear, double newPrice) {
        for (Car car : cars) {
            if (car.getCarId().equals(carId)) {
                car.setModelName(newModelName);
                car.setYear(newYear);
                car.setPrice(newPrice);
                break;
            }
        }
    }

    public void deleteCar(String carId) {
        cars.removeIf(car -> car.getCarId().equals(carId));
    }
}

public class Project3 {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        CarDealership carDealership = new CarDealership();

        while (true) {
            try {
                System.out.println("1. Add Car");
                System.out.println("2. Display Cars");
                System.out.println("3. Update Car");
                System.out.println("4. Delete Car");
                System.out.println("5. Exit");
                System.out.print("Enter your choice: ");

                int choice = scanner.nextInt();
                scanner.nextLine(); // Consume the newline character

                switch (choice) {
                    case 1:
                        System.out.print("Enter car ID: ");
                        String carId = scanner.nextLine();
                        System.out.print("Enter car model: ");
                        String modelName = scanner.nextLine();
                        System.out.print("Enter car year: ");
                        int year = scanner.nextInt();
                        System.out.print("Enter car price: $");
                        double price = scanner.nextDouble();
                        scanner.nextLine(); // Consume the newline character
                        Car newCar = new Car(carId, modelName, year, price);
                        carDealership.addCar(newCar);
                        break;

                    case 2:
                        carDealership.displayCars();
                        break;

                    case 3:
                        System.out.print("Enter car ID to update: ");
                        String updateCarId = scanner.nextLine();
                        System.out.print("Enter new model: ");
                        String newModelName = scanner.nextLine();
                        System.out.print("Enter new year: ");
                        int newYear = scanner.nextInt();
                        System.out.print("Enter new price: $");
                        double newPrice = scanner.nextDouble();
                        scanner.nextLine(); // Consume the newline character
                        carDealership.updateCar(updateCarId, newModelName, newYear, newPrice);
                        break;

                    case 4:
                        System.out.print("Enter car ID to delete: ");
                        String deleteCarId = scanner.nextLine();
                        carDealership.deleteCar(deleteCarId);
                        break;

                    case 5:
                        System.out.println("Exiting program.");
                        System.exit(0);

                    default:
                        System.out.println("Invalid choice. Please try again.");
                }
            } catch (InputMismatchException e) {
                System.out.println("Invalid input. Please enter a number.");
                scanner.nextLine(); // Consume the invalid input
            } catch (Exception e) {
                System.out.println("An error occurred: " + e.getMessage());
            }
        }
    }
}
