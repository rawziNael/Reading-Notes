# Inheritance and Interfaces  

#### Inheritance  
Definitions: A class that is derived from another class is called a subclass (also a derived class, extended class, or child class). The class from which the subclass is derived is called a superclass (also a base class or a parent class).  
Excepting Object, which has no superclass, every class has one and only one direct superclass (single inheritance).  
To inherit from a class, use the extends keyword.  
 ![inherit](/assets01/Java-Inheritance.webp)  

Example on inheritance:  
![example](/assets01/inhex.png)  

#### Interfaces  
Another way to achieve abstraction in Java, is with interfaces.  
An interface is a completely "abstract class" that is used to group related methods with empty bodies  

```
// interface
interface Animal {
  public void animalSound(); // interface method (does not have a body)
  public void run(); // interface method (does not have a body)
}
```  
A Java interface contains static constants and abstract methods.  
To access the interface methods, the interface must be "implemented" (kinda like inherited) by another class with the implements keyword (instead of extends). The body of the interface method is provided by the "implement" class:  

```
// Interface
interface Animal {
  public void animalSound(); // interface method (does not have a body)
  public void sleep(); // interface method (does not have a body)
}

// Pig "implements" the Animal interface
class Pig implements Animal {
  public void animalSound() {
    // The body of animalSound() is provided here
    System.out.println("The pig says: wee wee");
  }
  public void sleep() {
    // The body of sleep() is provided here
    System.out.println("Zzz");
  }
}
```  
The relationship between classes and interfaces:  
  
![example](/assets01/68747470733a2f2f7374617469632e6a61766174706f696e742e636f6d2f696d616765732f636f72652f696e7465726661636572656c6174696f6e2e6a7067.jfif)  


