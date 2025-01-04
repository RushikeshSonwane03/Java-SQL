
# Aggregation :
- Aggregation is a term which is used to represent one way relationship between two objects.
- In java, Aggregation represents **Has-A** relationship, which means when a class contains reference of another class known to have Aggregation.
- If a class have an entity reference, it is known as Aggregation.


## Inheritance vs Aggregation
| Inheritance | Aggregation |
| ------------- | ------------ | 
| Is-A Relationship | Has-A Relationship |
| Parent-Child Relationship | Non Blood Relationship |
|Tightly Coupled | Loosely Coupled |
| Case: If all methods of parent class to be accessed by child class. | Case: If some specific methods of parent class to be accessed by child class. |



- Example 1 :
```sh
package day18_13Sept;

class College{
	public void office() {
		System.out.println("This is My Office");
	}
	public void classroom() {
		System.out.println("BCA Class");
	}
	public void staffroom() {
		System.out.println("Allowed only Staff");
	}
}

class Student extends College{
	College c1 = new College();
	
	public void display() {
		System.out.println("My name : RUSHIKESH ");
	}
	
}

public class demo_aggregation {
	public static void main(String[] args) {
		Student s1 = new Student();
		s1.display();
		s1.c1.classroom();
	}
}

- Output :- 
My name : RUSHIKESH 
BCA Class
```
- Example 2:
```sh
package day18_13Sept;

class Address{
	String city;
	int pincode;
	String state;
	String country;
	public Address(String city,	int pincode, 
			String state, String country) {
		this.city = city;
		this.pincode = pincode;
		this.state = state;
		this.country = country;
	}
}

class Employee{
	int eid;
	String ename;
	String eemail;
	Address a1;
	public Employee(int eid, String ename, 
			String eemail, Address a1) {
		this.eid = eid ;
		this.ename = ename ;
		this.eemail = eemail ;
		this.a1 = a1;
	}
	
	void display() {
		System.out.println("Employee Id : " + eid);
		System.out.println("Employee Name : " + ename);
		System.out.println("Employee Email : " + eemail);
		System.out.println("Employee City : " + a1.city);
		System.out.println("Employee Pincode : " + a1.pincode);
		System.out.println("Employee State : " + a1.state);
		System.out.println("Employee Country : " + a1.country);
	}
}

public class demo2_aggregation {
	public static void main(String[] args) {
		Address ap = new Address("Dhule", 424002, "Maharashtra", "India");
		
		Employee e1 = new Employee(101, "Rushi", "Rushi@gmail.com",ap);
		e1.display();
	}
}

- Output : 
Employee Id : 101
Employee Name : Rushi
Employee Email : Rushi@gmail.com
Employee City : Dhule
Employee Pincode : 424002
Employee State : Maharashtra
Employee Country : India
```
