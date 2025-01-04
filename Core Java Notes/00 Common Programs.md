# Swap two Numbers :
```sh
package first;
public class Swap_two_numbers {
	public static void main(String[] args) {
		int a = 2;  // First Number
		int b = 5;  // Second Number

		System.out.println(" Before Swapping :");
		System.out.println(" a = " + a);
		System.out.println(" b = " + b);
		
		// Method 1 : With Using Third Variable
		int c;
		
		c = a;
		a = b;
		b = c;

		System.out.println(" After Swapping (With Third Variable) :");
		System.out.println(" a = " + a);
		System.out.println(" b = " + b);
		
		// Method 2 : Without Using Third Variable
		b = b + a; 
		a = b - a;
		b = b - a;

		System.out.println(" After Swapping (Without Third Variable) :");
		System.out.println(" a = " + a);
		System.out.println(" b = " + b);	
	}
}

- Output :
 Before Swapping :
 a = 2
 b = 5
 After Swapping (With Third Variable) :
 a = 5
 b = 2
 After Swapping (Without Third Variable) :
 a = 2
 b = 5
```


# Even-Odd-Zero Number :
```sh
package first;
import java.util.Scanner;

public class Odd_Even_Zero {

	public static void main(String[] args) {
		int number;
		Scanner s1 = new Scanner(System.in);
		System.out.print(" Enter Number : ");
		number = s1.nextInt();
		
		if(number == 0) {
			System.out.println(number + " is Zero.");
		}
		else if(number  % 2 == 0 ) {
			System.out.println(number + " is Even Number.");
		}
		else {
			System.out.println(number + " is Odd Number.");
		}
		
	}

}
```


# Fibonacci Series


# Perfect Number



# Armstrong Number :
- 153 = (1x1x1) + (5x5x5) + (3x3x3) = 1 + 125 + 27 = 153
    // 153 is an Armstrong Number
- 1243 = (1x1x1x1) + (2x2x2x2) + (4x4x4x4) + (3x3x3x3) = 1 + 16 + 256 + 81 = 354 
	// 354 is not an Armstrong Number
```sh
package first;
import java.util.Scanner;
public class Armstrong_number {
	public static void main(String[] args) {
		int number, result = 0 , remainder, digit = 0, temp, temp1;
		Scanner s1 = new Scanner(System.in);
		System.out.print(" Enter number : ");
		number = s1.nextInt();
		temp = number;
		temp1 = number;
		while(temp != 0) {
			digit += 1;
			temp /= 10;
		}
		System.out.println(" Digits : " + digit);		
		while(temp1 != 0) {
			remainder = temp1 % 10;
			result += Math.pow(remainder, digit);
			temp1 /= 10;
		}
		
		if(result == number) {
			System.out.println(number + " is an Armstrong Number");
		}
		else {
			System.out.println(number + " is not an Armstrong Number");
		}
	}
}

- Output :
 Enter number : 153
 Digits : 3
153 is an Armstrong Number
```

    


# Palindrome Number/String


# Factorial of a Number


# Reverse of a String


# Bubble Sort
# Selection Sort
# Insertion Sort
# Remove duplicate element from an Array