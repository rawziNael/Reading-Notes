# Java Basics
Java is a general-purpose, class-based, object-oriented programming language designed for having lesser implementation dependencies. It is a computing platform for application development. 
### Language Basics
#### Variables:
Variable in Java is a data container that saves the data values during Java program execution. Every variable is assigned a data type that designates the type and quantity of value it can hold. Variable is a memory location name of the data.

A variable is a name given to a memory location.

##### Types of variable in Java programming language:

- Instance Variables (Non-Static Fields):
Instance variables are created when an object is created with the use of the keyword 'new' and destroyed when the object is destroyed.
- Class Variables (Static Fields):
Static variables are created when the program starts and destroyed when the program stops.
- Local Variables:
A variable defined within a block or method or constructor is called a local variable.
- Parameters:
The important thing to remember is that parameters are always classified as "variables" not "fields".
##### Java variable naming conventions

For variables, the Java naming convention is to always start with a lowercase letter and then capitalize the first letter of every subsequent word. Variables in Java are not allowed to contain white space, so variables made from compound words are to be written with a lower camel case syntax.

Here are three examples of variables that follow the standard Java naming convention:
- firstName
- timeToFirstLoad
- index

#### Operators
Operators are symbols that perform operations on variables and values. For example, + is an operator used for addition, while * is also an operator used for multiplication.

Operators in Java can be classified into 5 types:
- Arithmetic Operators
- Assignment Operators
- Relational Operators
- Logical Operators
- Unary Operators
- Bitwise Operators

The following table represents most known operations with their precedence order:
![operator precedence(https://ucarecdn.com/4860994e-105d-456b-a98e-f3c51854830f/-/crop/478x539/214,123/-/preview/)

#### Expressions, Statements, and Blocks:
**Expression:** 
is the line of code that either holds or calculates these values.

**Statement:**
Think of a statement as a command to Java - an order to perform a task. The expression above only defined the variable; when we convert that expression into a statement, we will actually do something with it.
In the expression, we simply declared the variable for our user counter. The next line of code will take action on the variable. In the following example, we'll add a value (in this case another variable) to the user count:
An expression sets up the path while the statements perform actions on the variables.

**Blocks:**
Expressions and statements often need to be placed together. Let's say you have a module or function that carries out a task, such as updating a pay rate. Blocks are declared by using an open curly bracket ({) and a closing curly bracket (}).
