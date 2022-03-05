# Maps, primitives, File I/O  
In this file we will read about the following resources:  
- Primitives vs. Objects.
- Exceptions in Java.
- Using Scanner to read in a file in Java  
Java has a two-fold type system consisting of primitives such as int, boolean and reference types such as Integer, Boolean. Every primitive type corresponds to a reference type.  
Java performs a conversion between the primitive and reference types if an actual type is different from the declared one:
```
Integer j = 1;          // autoboxing
int i = new Integer(1); // unboxing  
```
The process of converting a primitive type to a reference one is called autoboxing, the opposite process is called unboxing.  
###  Single Item Memory Footprint
Just for the reference, the primitive type variables have the following impact on the memory:

- boolean – 1 bit
- byte – 8 bits
- short, char – 16 bits
- int, float – 32 bits
- long, double – 64 bits

And for a single instance of a reference type on this JVM occupies 128 bits except for Long and Double which occupy 192 bits:  

- Boolean – 128 bits
- Byte – 128 bits
- Short, Character – 128 bits
- Integer, Float – 128 bits
- Long, Double – 192 bits

## Exceptions  
What Is an Exception?  
An exception is an event that occurs during the execution of a program that disrupts the normal flow of instructions.  

### Types of Exceptions in Java  
![Exceptions](/assets01/types-of-exception-in-java.png)  

### The Catch or Specify Requirement
Valid Java programming language code must honor the Catch or Specify Requirement. This means that code that might throw certain exceptions must be enclosed by either of the following:  

A try statement that catches the exception. The try must provide a handler for the exception, as described in Catching and Handling Exceptions.  
A method that specifies that it can throw the exception. The method must provide a throws clause that lists the exception, as described in Specifying the Exceptions Thrown by a Method.  
```
try 
{
    //  Block of code to try
}
catch(Exception e) 
{ 
    //  Block of code to handle errors
}
```
### How to throw exceptions in Java
Throwing an exception is as simple as using the "throw" statement. You then specify the Exception object you wish to throw. Every Exception includes a message which is a human-readable error description. It can often be related to problems with user input, server, backend, etc.  
```
throw new Exception("Exception message");
``` 
### Scanner
The Scanner class is used to get user input, and it is found in the java. util package. To use the Scanner class, create an object of the class and use any of the available methods found in the Scanner class documentation.  
to import the Scanner : import java.util.Scanner  
```
Scanner scanner = new Scanner(System.in);  // Create a Scanner object
int userName = scanner.nextInt();  // Read user input
```
