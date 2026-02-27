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
public class UserRegistration {
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
class HelloThread extends Thread {
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
class WelcomeThread extends Thread {
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

```
# output
![7a output](https://github.com/user-attachments/assets/fe765d0b-f278-4293-8880-7dffc175756a)


# EXPERIMENT7b
## TITLE: To implement  extending thread
```
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
                Thread.sleep(2000);   // 2 seconds
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
                Thread.sleep(3000);   // 3 seconds
            }
        } catch (InterruptedException e) {
            System.out.println("WelcomeThread Interrupted");
        }
    }
}

// Main Class
public class TestThreads {

    public static void main(String[] args) {

        // Create thread objects
        GoodMorningThread t1 = new GoodMorningThread();
        HelloThread t2 = new HelloThread();
        WelcomeThread t3 = new WelcomeThread();

        // Start all threads
        t1.start();
        t2.start();
        t3.start();
    }
}

```
# output
![7b output](https://github.com/user-attachments/assets/e67fca84-aeaa-4d9f-8159-b6d3062b767e)




