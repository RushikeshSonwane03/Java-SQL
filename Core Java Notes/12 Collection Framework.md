# Collection Framework 

- Collection Framework - Jdk 1.2+ -> (**import java.util.\***)
- Collection Framework is added in Java to introduce Data Structures and Algorithms in Java.
- In collection we can store Non-primitive type of Data only. (Heterogeneous type of Data) [Object/Multiple type of Data]
- Predefined Classes and Interfaces that we can use Directly. 
- Collection -> List, Set, Map, Array List, Linked List, Graph, Tree
- Collection <- Interface(Abstract Methods only) || Collections <- Class (Utility class <- Only Static Methods)
  
## Data Structure :
- To Store and Manage Data in well structured & characterised manner in Efficient way.
### Types of Data Stuctures : 
1. Primitive Data Stuctures : (Single Entity stored in a DS) - Int, Char, Float, Double, Short, Boolean
2. Non-Primitive Data Stuctures : (Multiple Entities are stored in a DS) 
   1. Linear : Data Stored in sequencial fashion. - Array, String, List, Set, Map, Array List, Linked List
   2. Non-Linear : Data Stored in random fashion. - Graph, Tree

## Introduction:-
1. Collection Framework
2. Map Framework

## 1. Collection Framework

**Hierarchy of Collection Framework :-**
![Hierarchy of Collection Framework](Hierarchy_of_Collection_Framework.png)


### ArrayList :
- ArrayList is a class which is implemented by List Interface  
- Data Structure implemented in it is " Resizable Array ".
- Syntax :
```sh
class ArrayList implements List{
    Methods
    Constructors
}
```
- Example :
```sh
package day22_23Sept;

import java.util.*;

public class ArrayList_Class_Demo {

	public static void main(String[] args) {
		
		ArrayList a1 = new ArrayList();
		a1.add(10);
		a1.add(56);
		a1.add("Rushikesh");
		a1.add(2.3);
		a1.add('A');
		a1.add("Rushikesh");
		a1.add(null);

		System.out.println(a1);
		System.out.println(a1.size());
		System.out.println(a1.isEmpty());
		System.out.println(a1.indexOf(2.3));
	}
}


- Output :
[10, 56, Rushikesh, 2.3, A, Rushikesh, null]
5
false
3
```
- Important points of ArrayList :
  - It is Index Based Data Structure.
  - It follows Insertion Order.
  - It allows Duplicate Values.
  - It allows multiple null valued data.
  - ArrayList class are non synchronized.
  - ArrayList is worst for Insertion and Deletion.
  - But ArrayList is Better for Searching. 

