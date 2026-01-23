# EXPERIMENT3
## TITLE: 3a.)implement constructor overloading in JAVA
```
class Student {

	String name;
	int age;
	double marks;

	Student() {

	}

	Student(String name, int age, double marks) {

		this.name=name;
		this.age=age;
		this.marks=marks;

	}

	void display() {

		System.out.println("Name: "+name);
		System.out.println("Age: "+age);
		System.out.println("marks: "+marks);
}

	}
class Main {

	public static void main(String args[]) {

		Student std = new Student();
		std.display();

		Student std1 = new Student("Hari", 40, 67.8);
		std1.display();

	}
}
```
# OUTPUT
<img width="269" height="149" alt="3a output" src="https://github.com/user-attachments/assets/0e4d8bb4-b1af-4cbd-ad4e-58e299160344" />



