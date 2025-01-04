# Package :
- A package in java is used to group related classes.
- A folder in a file directory.
- Java Package is used to categorize the classes and interfaces so that they can be easily maintained.

## Types of Package :
    1. Built-in Packages
    2. User Defined 

1. Built-in Packages :
    Example : Lang, util, sql, io
2.  User Defined 
    Example :
```sh

// Package : package_demo - 1. Laptop, 2. Book, 3. Pen
// 1. Laptop
package package_demo;
public class Laptop {
	public void get() {
		System.out.println("This is My Laptop");
	}
}
// 2. Book
package package_demo;
public class Book {
	public void show() {
		System.out.println("Please read the Book !");
	}
}
// 3. Pen
package package_demo;
public class Pen {
	public void display() {
		System.out.println("Thank You !!!");
	}
}

// Main Class and Method
package day18_13Sept;

import package_demo.Laptop; 

import package_demo.Book; 

import package_demo.Pen; 

public class demo_packages {
	public static void main(String[] args) {
		
		Laptop l1 = new Laptop();
		l1.get();
		
		Book b1 = new Book();
		b1.show();
		
		Pen p1 = new Pen();
		p1.display();
	}
}

- Output :
This is My Laptop
Please read the Book !
Thank You !!!
```

## Ways to Access Package :
1. **import**.package_name.*;
2. **import**.package_name.class_name;
3. Fully qualified name.

- Examples :
```sh
// 1.
package day18_13Sept;
import package_demo.*; 
public class demo_packages {
	public static void main(String[] args) {
		Laptop l1 = new Laptop();
		l1.get();		
		Book b1 = new Book();
		b1.show();		
		Pen p1 = new Pen();
		p1.display();
	}
}

// 2.
package day18_13Sept;
import package_demo.Laptop; 
import package_demo.Book; 
import package_demo.Pen; 
public class demo_packages {
	public static void main(String[] args) {		
		Laptop l1 = new Laptop();
		l1.get();		
		Book b1 = new Book();
		b1.show();		
		Pen p1 = new Pen();
		p1.display();
	}
}

// 3.
package day18_13Sept;
public class demo_packages {
	public static void main(String[] args) {		
		package_demo.Laptop l1 = new package_demo.Laptop();
		l1.get();		
		package_demo.Book b1 = new package_demo.Book();
		b1.show();		
		package_demo.Pen p1 = new package_demo.Pen();
		p1.display();
	}
}
```

