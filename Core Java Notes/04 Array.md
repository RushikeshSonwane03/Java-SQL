# Array

- Defn : Array is a Collection of same type of Data (homogeneous type of data).
- It has Fixed Size. we cannot increase or decrease at Runtime.
- We can access the data in an array using its index.

### Advantages of using Array :
1. Code Optimization
2. Random access
3. Sorting Easily

### Disadvantages of using Array :
1. For Insetion and Deletion Array is worst. (lots of Index shifting occurs)
2. Fixed Sized
3. Memory Wastage


## Types of Array :
1. 1-Dimensional Array
2. 2-Dimensional Array
3. Multi Dimensional Array



### 1-Dimensional Array :
- Syntax : datatype array_name[] = new datatype[array_size];
        - int arr[] = new int[20];
        - new = Keyword for Memory Allocation
        - int[20] = Allocation of memory to array 'arr' for 20 integer type values.
- Example :
```sh
package day5_27Aug;

public class Array {

	public static void main(String[] args) {


		int a[] = new int[5]; // Array Declaration
		
		a[0] = 10;
		a[1] = 20;
		a[2] = 30;
		a[3] = 40;
		a[4] = 50;
		
		for(int i = 0; i < 5; i++) {
			System.out.print(a[i] + "\t");
		}

	}

}
```

- Array : 
    a[0]    a[1]    a[2]    a[3]    a[4]     <= Array[indexes]
    10      20      30      40      50       <= Array[Values]

### 2-Dimensional Array :
- Syntax : datatype array_name[][] = new datatype[array_rows][array_cols];
        - int arr[][] = new int[rows][columns];
        - new = Keyword for Memory Allocation
        - int[3][3] = Allocation of memory to array 'arr' for 3x3 Matrix (9 values -> 3 in each row) integer type values.
- Example :
```sh
package day6_28Aug;

import java.util.*;

public class TwoD_multi_dim_array {

	public static void main(String[] args) {
		int a[][]= new int[3][3];
		int i, j;
		
		Scanner s1 = new Scanner(System.in);
		
		System.out.println("Accept array :");
		for(i=0; i<=2; i++) {
			for(j=0;j<=2;j++) {
				a[i][j] = s1.nextInt();
			}
		}
		
		System.out.println("Display array :");
		for(i=0; i<=2; i++) {
			for(j=0;j<=2;j++) {
				System.out.print(a[i][j] + "\t");
			}
			System.out.println();
		}
		
	}

}


Output -

Accept array :
1
2
3
4
5
6
7
8
9
Display array :
1	2	3	
4	5	6	
7	8	9	
```	

### Multi-Dimensional Array :
- Syntax : datatype array_name[][][] = new datatype[no_of_matrices][rows][cols];
        - int arr[][][] = new int[k][i][j];
        - new = Keyword for Memory Allocation
        - int[k][i][j] = Allocation of memory to array 'arr' for k matrices (iXj size) of integer type values.
- Example :
```sh
package day6_28Aug;

import java.util.Scanner;

public class multi_dim_Array {

	public static void main(String[] args) {
		int a[][][] = new int[2][3][3];
		int i, j, k;
		
		Scanner s1 = new Scanner(System.in);
		
		System.out.println("Accept array :");
		for(k=0; k<=1; k++){
			for(i=0; i<=2; i++) {
				for(j=0;j<=2;j++) {
					a[k][i][j] = s1.nextInt();
				}
			}
			
		}
		
		System.out.println("Display array :");
		for(k=0; k<=1; k++){
			for(i=0; i<=2; i++) {
				for(j=0;j<=2;j++) {
					System.out.print(a[k][i][j] + "\t");
				}
				System.out.println();
			}
			System.out.println();
			
		}
		
	}

}

Output -

Accept array :
1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
16
17
18
Display array :
1	2	3	
4	5	6	
7	8	9	

10	11	12	
13	14	15	
16	17	18
```

