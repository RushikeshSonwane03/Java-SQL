```sh
package user_input;
// Package for Scanner Class of java.util package.
import java.util.*;

public class user_input_scanner_method {

	public static void main(String[] args) {
		int a, b, c;
		Scanner s1 = new Scanner(System.in);
		System.out.print(" Enter first number : ");
		a = s1.nextInt();
		System.out.print(" Enter second number : ");
		b = s1.nextInt();
		
		c = a + b;
		System.out.println(" Sum : " + c);

	}

}
```