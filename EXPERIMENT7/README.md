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


# EXPERIMENT7c
## TITLE: To implement alive
```

// Class that simulates a long-running task
class LongRunningTask extends Thread {

    @Override
    public void run() {
        try {
            System.out.println("Long running task started...");

            // Simulate 5 seconds of work
            for (int i = 1; i <= 5; i++) {
                System.out.println("Working... " + i);
                Thread.sleep(1000);   // 1 second delay
            }

            System.out.println("Long running task completed!");
        } catch (InterruptedException e) {
            System.out.println("Thread was interrupted.");
        }
    }
}

// Main class
public class ThreadDemo {

    public static void main(String[] args) {

        // Create thread object
        LongRunningTask task1 = new LongRunningTask();

        // Check isAlive() before starting
        System.out.println("Before starting task1: " + task1.isAlive());

        // Start the thread
        task1.start();

        // Check isAlive() after starting
        System.out.println("After starting task1: " + task1.isAlive());

        try {
            System.out.println("Main thread waiting for task1 to complete using join()...");

            // Main thread waits for task1 to finish
            task1.join();

        } catch (InterruptedException e) {
            System.out.println("Main thread interrupted.");
        }

        // Check isAlive() after join()
        System.out.println("After join(): " + task1.isAlive());

        System.out.println("Main thread continues after task1 completed.");
    }
}

```
# output
![7c output](https://github.com/user-attachments/assets/87791249-f822-4211-a395-aae9d123bcff)





