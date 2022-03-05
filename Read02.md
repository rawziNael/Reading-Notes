# Arrays, Loops, Imports
#### Loops
Looping in programming languages is a feature which facilitates the execution of a set of instructions/functions repeatedly while some condition evaluates to true.  
In Java we have different types of loops:  
1- For loop
```
  for(int i=0;i<10;i++){
    System.out.println(i);
  }

```
2- While loop  
A "While" Loop is used to repeat a specific block of code an unknown number of times, until a condition is met.
```
  int i = 0;
while (i < 5) {
  System.out.println(i);
  i++;
}
```
3- Do while loop  
The Java do-while loop is used to iterate a part of the program repeatedly, until the specified condition is true. If the number of iteration is not fixed and you must have to execute the loop at least once, it is recommended to use a do-while loop.
```
int i = 0;
do {
  System.out.println(i);
  i++;
}
while (i < 5);
```
### Packages
Package in Java is a mechanism to encapsulate a group of classes, sub packages and interfaces.  
```
Packages are used for:
1- Preventing naming conflicts.
2- Providing controlled access.
```
Package declaration syntax:
```
package illustration;  //1) Package statment (optional).

import java.awt.*;     //2) Imports (optional).

public class Drawing {// 3) Class or interface definitions.
```
### Import  
The import keyword is used to import a package, class or interface.  
The JOptionPane class is in the swing package, which is located in the javax package. The wildcard character (*) is used to specify that all classes with that package are available to your program. This is the most common programming style.
```
import java.util.Scanner;

class MyClass {
  public static void main(String[] args) {
    Scanner myObj = new Scanner(System.in);
    System.out.println("Enter username");

    String userName = myObj.nextLine();
    System.out.println("Username is: " + userName);
  }
}
```
