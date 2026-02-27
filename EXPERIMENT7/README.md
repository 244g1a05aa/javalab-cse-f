# EXPERIMENT7a
## TITLE: To implement user defined exception
```
class InvalidCountryException extends Exception {
    public InvalidCountryException() {
        super();
    }
    public InvalidCountryException(String message) {
        super(message);
    }
}
// Main Class
public class UserRegistration {

    // Method to register user
    public void registerUser(String userName, String userCountry)
            throws InvalidCountryException {

        if (!userCountry.equalsIgnoreCase("India")) {
            // Throw custom exception
            throw new InvalidCountryException(
                    "User outside India cannot be registered");
        } else {
            System.out.println("User registration done successfully");
        }
    }
    public static void main(String[] args) {

        UserRegistration ur = new UserRegistration();
        try {
            ur.registerUser("Ravi", "USA");
        } catch (InvalidCountryException e) {
            System.out.println(e.getMessage());
        }
        try {
            ur.registerUser("Anita", "India");
        } catch (InvalidCountryException e) {
            System.out.println(e.getMessage());
        }
    }
}
// First Thread - Prints "Good Morning" every 1 second
class GoodMorningThread extends Thread {

    @Override
    public void run() {
        try {
            while (true) {
                System.out.println("Good Morning");
                Thread.sleep(1000);   // 1 second
            }
        } catch (InterruptedException e) {
            System.out.println("GoodMorningThread Interrupted");
        }
    }
}

// Second Thread - Prints "Hello" every 2 seconds
class HelloThread extends Thread {

    @Override
    public void run() {
        try {
            while (true) {
                System.out.println("Hello");
                Thread.sleep(2000);  
            }
        } catch (InterruptedException e) {
            System.out.println("HelloThread Interrupted");
        }
    }
}

// Third Thread - Prints "Welcome" every 3 seconds
class WelcomeThread extends Thread {

    @Override
    public void run() {
        try {
            while (true) {
                System.out.println("Welcome");
                Thread.sleep(3000);  
            }
        } catch (InterruptedException e) {
            System.out.println("WelcomeThread Interrupted");
        }
    }
}


