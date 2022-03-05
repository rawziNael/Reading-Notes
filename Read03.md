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
