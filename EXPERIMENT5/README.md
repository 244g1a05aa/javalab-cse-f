# EXPERIMENT5a
## TITLE: To implement inheritance
```

import java.util.Scanner;

interface Sortable {
    void sort(int[] arr);
}

class BubbleSort implements Sortable {
    public void sort(int[] arr) {
        int n = arr.length;
        for (int i = 0; i < n - 1; i++) {
            for (int j = 0; j < n - i - 1; j++) {
                if (arr[j] > arr[j + 1]) {
                    int temp = arr[j];
                    arr[j] = arr[j + 1];
                    arr[j + 1] = temp;
                }
            }
        }
    }
}

class SelectionSort implements Sortable {
    public void sort(int[] arr) {
        int n = arr.length;
        for (int i = 0; i < n - 1; i++) {
            int min = i;
            for (int j = i + 1; j < n; j++) {
                if (arr[j] < arr[min]) {
                    min = j;
                }
            }
            int temp = arr[min];
            arr[min] = arr[i];
            arr[i] = temp;
        }
    }
}

public class TestSort {

    static void printArray(int[] arr) {
        for (int x : arr) {
            System.out.print(x + " ");
        }
        System.out.println();
    }

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        System.out.print("Enter number of elements for Bubble Sort: ");
        int n1 = sc.nextInt();

        int[] arr1 = new int[n1];
        System.out.println("Enter elements:");
        for (int i = 0; i < n1; i++) {
            arr1[i] = sc.nextInt();
        }

        Sortable ref = new BubbleSort();
        ref.sort(arr1);

        System.out.println("Array sorted using Bubble Sort:");
        printArray(arr1);

        System.out.print("Enter number of elements for Selection Sort: ");
        int n2 = sc.nextInt();

        int[] arr2 = new int[n2];
        System.out.println("Enter elements:");
        for (int i = 0; i < n2; i++) {
            arr2[i] = sc.nextInt();
        }

        ref = new SelectionSort();
        ref.sort(arr2);

        System.out.println("Array sorted using Selection Sort:");
        printArray(arr2);

        sc.close();
    }
}

```


# output
<img width="624" height="235" alt="5a" src="https://github.com/user-attachments/assets/e8c6de17-6c36-46fd-843b-3fdc92947209" />


# EXPERIMENT5b
## TITLE: To implement runtime polymorphism
```

import java.util.Scanner;

class Vehicle {
    public void run() {
        System.out.println("Vehicle is running");
    }
}

class Car extends Vehicle {
    @Override
    public void run() {
        System.out.println("Car is running on four wheels");
    }
}

class Bike extends Vehicle {
    @Override
    public void run() {
        System.out.println("Bike is running on two wheels");
    }
}

public class TestVehicle {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        Vehicle v;

        System.out.println("Choose vehicle type:");
        System.out.println("1. Car");
        System.out.println("2. Bike");

        int choice = sc.nextInt();

        if (choice == 1) {
            v = new Car();
        } else if (choice == 2) {
            v = new Bike();
        } else {
            v = new Vehicle();
        }

        v.run();
        sc.close();
    }
}
```

# output
<img width="600" height="181" alt="5b" src="https://github.com/user-attachments/assets/264a2325-3d76-4499-bd28-e014a0a2d293" />



