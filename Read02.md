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

