# <p align = "center"> Fundamentals of Java Programming Language </p>

<p align="center"><img src="https://res.cloudinary.com/practicaldev/image/fetch/s--bR8fvvmK--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/q4viwvy7lfuq4i1z72ut.png"/></p>

---
### <p align="center">"Everything is an Object in Java"</p>
---

##  <img src="https://marcus-biel.com/wp-content/themes/marcus-biel/images/wizard.png" width="80" height="80"> Introduction to Java

### What is Java?

Java is a programming language and a platform. Java is a high level, robust, object-oriented and secure programming language.

### Types of Java Applications

- __Standalone Application__

Standalone applications are also known as desktop applications or window-based applications. These are traditional software that we need to install on every machine.

- __Web Application__

An application that runs on the server side and creates a dynamic page is called a web application. Currently, `Servlet`, `JSP`, `Struts`, `Spring`, `Hibernate`, `JSF`, etc.

- __Enterprise Application__

An application that is distributed in nature, such as banking applications, etc. is called an enterprise application. It has advantages like high-level security, load balancing, and clustering. In Java, `EJB` is used for creating enterprise applications.

- __Mobile Application__

An application which is created for mobile devices is called a mobile application. Currently, Android and Java `ME` are used for creating mobile applications.

### Java Platforms/Editions

There are 4 platforms or editions of Java

- __Java SE (Java Standard Edition)__

It is a Java programming platform. It includes Java programming API such as `java.lang`, `java.io`, `java.net`, `java.util`, `java.sql`, `java.math`, etc. It includes core topics like OOPs, String. Regex, Exception, Inner Classes, Multithreading, I/O Stream, Networking, AWT, Swing, Reflection, Collection,...

- __Java EE (Java Enterprise Edition)__

It is an enterprise platform that is mainly used to develop web and enterprise applications. It is built on top of the Java SE platform. It includes topics like `Sevlet`,`JSP`, `Web Services`, `EJB`, `JPA`,...

- __Java ME (Java Micro Edition)__

It is a micro platform that is dedicated to mobile applications.

- __Java FX__

It is used to develop rich internet applications. It uses a lightweight user interface API

## JDK, JRE, adn JVM

<p align="center"><img src="https://res.cloudinary.com/practicaldev/image/fetch/s--r3p4Ep-o--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/om46l2j3ke10a1f3fmyx.png"/></p>

JDK = JRE + Development Tool
JRE = JVM + Library Classes

## First Java Program

Let's write a sample Hello World application

``` java 
/**
 * This is very first simple Java program.
 * FileName: "Main.java"
 */

import java.util.*;
import java.io.*;
import java.lang.*;

public class Main {
  public static void main(String[] args) {
    // Prints "Hello, World" to the terminal window.
    System.out.println("Hello, World");
  }
}
```
Notice that when we declare a public class, we must declare it inside a file with __the same name__ (Main.java), otherwise we'll get an error when compiling.

Now open the  the terminal / Command Prompt. Change your current directory in the terminal / Command Prompt to the directory where your file is located. And compile the file :

```
$ javac Main.java
```

Now run the file using `java` command!

```
$ java Main
Hello, World
```

## Commnents 

- Comments in a program are called _inline documentation_
- They should be included to explain the purpose of the program and describe processing steps
- They do not affect how a program works
- Java comments can take three forms:

``` java
  // this comment run to the end of the line
  
  /* this comment runs to the terminating 
   * symbol, even across line breaks 
   */

  /** 
   * this is a javadoc comment 
   */
   
```
## Data Types

In Java, there are two kinds of data types:

### Primitive data type
- The primitive Data Types are built-in data types and they specify the type of value stored in a variable and the memory size. The primitive data types do not have any additional methods
- The primitive data types includes `byte`, `short`, `int`, `long`, `float`, `double`, `char`, `boolean`

The following table provides more description of each primitive data type.

| PRIMITIVE TYPE    | STORAGE SIZE (byte) | STORAGE SIZE(bit) | RANGES |
|-------------------|:-------------------:|:-----------------:|:------:|
| `byte`  			|  `1 byte`  		  |  `8 bits`  | 8-bit signed integer within the range of -128 to 127 |
| `short`   		|  `2 bytes`  		  |  `16 bits` | 16-bit signed integer within the range of -32,768 to 32,767 |
| `int`   			|  `4 bytes`  		  |  `32 bits` | 32-bit signed integer within the range of -2147483648 to 2147483647 |
| `long`       		|  `8 bytes`  		  |  `64 bits` | 64-bit signed integer within the range of -9223372036854775808 to 9223372036854775807 |
| `float`       	|  `4 bytes`   		  |  `32 bits` | single-precision 32-bit floating point within the range of 1.4E-45 to 3.4028235E38 |
| `double`     	 	|  `8 bytes`  		  |  `64 bits` | double-precision 64-bit floating point within the range of 4.9E-324 to 1.7976931348623157E308 |
| `char`   			|  `2 bytes`  		  |  `16 bits` | single 16-bit Unicode character within the range of `\u0000` (or 0) to `\uffff` (or 65,535 inclusive) |
| `boolean`   		|  `1 byte`  		  |     	   | It can be either `true` or `false` |

### Non-primitive or reference data type
- Non-primitive data types are the reference data types or user-created data types. All non-primitive data types are implemented using object concepts.Every variable of the non-primitive data type is an object. The non-primitive data types may use additional methods to perform certain operations. The default value of non-primitive data type variable is `null`.
- In Java, examples of non-primitive data types are `String`, `Array`, `List`, `Queue`, `Stack`, `Class`, `Interface`

## Type Conversion or Type Casting

Type conversion in Java can be either `implicit` or `explicit`

### Widening Type Casting (automatically)
When the compiler converts a smaller type of data to a larger one automatically, it's known as an implicit or narrowing type conversion. The flow of conversion should be as follows:

<p align="center"><img src="https://static.studytonight.com/java/images/widening-type-conversion.jpg"/></p>

``` java
public class Main {
  public static void main(String[] args) {
    int myInt = 9;
    double myDouble = myInt;   // automatic casting: int to double
    
    System.out.println(myInt);    // Outputs 9
    System.out.println(myDouble);   // Outputs 9.0
  }
}
```

### Narrowing Type Casting (manually)
If we try to convert a larger data type to a smaller one, we need to add the `(data_type)` cast opeator explicitly.
The flow of conversion in this case will be the opposite of what you've seen already:

<p align="center"><img src="https://static.studytonight.com/java/images/narrowing-type-conversion.jpg"/></p>

``` java
public class Main {
  public static void main(String[] args) {
    double myDouble = 9.78d;
    int myInt = (int) myDouble;   // manual casting: double to int
    
    System.out.println(myDouble);   // Outputs 9.78
    System.out.println(myInt);    // Outputs 9
  }
}
```
## Java Autoboxing and Unboxing

<p align="center"><img src="https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Ftse2.mm.bing.net%2Fth%3Fid%3DOIP.Ttlsj2OxOySyqHj2puQofAHaDM%26pid%3DApi&f=1"/></p>

### Java Autoboxing - Primitive Types to Wrapper Objects

In __autoboxing__, the Java compiler automatically converts primitve types into their corresponding wrapper class objects. For example,

``` java
int a = 56;

// autoboxing
Integer aObj = a;
```

### Java Unboxing - Wrapper Objects to Primitive Types

In __unboxing__, the Java compiler automatically converts wrapper class objects into their conrresponding primitive types. For example,

``` java
// autoboxing 
Integer aObj = 56;

// unboxing
int a = aObj;
```

### Autoboxing and Unboxing together

``` java
import java.util.ArrayList;

class Main {
  public static void main(String[] args) {
    
    ArrayList<Integer> numbers = new ArrayList<>();
    
    // autoboxing
    numbers.add(5);
    numbers.add(4);
    numbers.add(7);
    
    System.out.println("ArrayList: " + numbers);
    
    // unboxing 
    int number = numbers.get(0);
    System.out.println("Value at index 0: " + number);
  }
}
```

## Escapse Sequences 

Some Java Escape sequences:

- `\b`  backspace
- `\t`  tab
- `\n`  newline
- `\r`  carriage return
- `\""` double quote
- `\'`  single quote
- `\\` backslash

## Variable

Variable is name for a location in memory

- Static variable: belong to its class, and it is shared by all class instances, with the same values

- Instance variable: a class variabel without the _static_ modifier, is shared by all class instaces, but its values can differ in different instances

- Local Variable: is created within a method or instance in a {} block. Its scope is limited within the block.
 
### Declaration variable

Variable must be declared by specifying the variabel's name and the type of information that it will hold

### Intilization variable

Variable can be given an initial value in the declaration

When a variable is referenced in a program, its current value is used

### Assignment

An assignment statement changes the values of a variable

The assignment operator is the `=` sign

 ``` java 
 total = 55;
 ```
 The expression on the right is evaluated and the result is stored in the variable on the left

 The value that was in `total` is overwritten
 
 You can only assign a value to a variable that is consistent with the variable's declared type. 

### Constants

A contant is an identifier that is similar to a variable except that it hold the same value during its entire existence

As the name implies, it is constant, not variable

The compiler will issue an error if you try to change the value of a constant

In Java, we use the `final` modifier to declare a constant

```java 

final int MIN_HEIGHT = 69;
```

## Varargs
### Syntax of Varargs
The syntax for implementing varargs in as follows:
```
accessModifier methodName(dataType... args) {
  // method body
}
```

> __Note__: 
> - While defining method signature, always keep varargs at last
> - A method can have only one varargs parameter

### Expamples

``` java
class Main {
	private void test(int... args) {
		int sum =0;
		for( int i : args) {
			sum += i;
		}
		System.out.println("Sum is: " + sum);
	}

	private void test(boolean p, String... args) {
		boolean negate = !p;
		System.out.println("negate " + negate);
		System.out.println("args.length " + args.length);
	}

	public static void main(String[] args) {
		Main obj = new Main();
		obj.test(1,2,3);
		obj.test(true, "hello", "world");
	}
}
```

## Operators

### Arithmetic Operators

| OPERATOR     | OPERATION |
|--------------|:---------:|
|	`+`	| Addition |
|	`-`	| Substraction |
|	`*`	| Multiplication |
|	`/`	| Division |
|	`%`	| Remainder (Modulo/Modulus) |

### Assignment Operators
| OPERATOR     | OPERATION | EQUIVALENT TO |
|--------------|:---------:|:---------:|
| `+=` | `a += b` | `a = a + b` |
| `-=` | `a -= b` | `a = a - b` |
| `*=` | `a *= b` | `a = a * b` |
| `/=` | `a /= b` | `a = a / b` |
| `%=` | `a %= b` | `a = a % b` |

### Relational Operators

| OPERATOR     | EXPLANATION | USAGE |
|--------------|:---------:|:---------:|
| `==` | Is Equal To | `5 == 8` returns `false` |
| `!=` | Is Not Equal To | `5 != 8` returns `true` |
| `>` | Is Greater Than | `5 > 8` returns `false` |
| `<` | Is Less Than | `5 < 8` returns `true` |
| `>=` | Greater Than or Equal To | `5 >= 8` returns `false` |
| `<=` | Less Than or Equal To | `5 <= 8` returns `true` |

There aren't that many operators to use in conditional statements and most of them are pretty straight forward:

``` java
public class Main{
	public static void main(String[] args) {
		int a = 4;
		int b = 5;
		boolean result;
		result = a < b; // true
		result = a > b; // false
		result = a <= 4; // a smaller or equal to 4 - true
		result = b >= 6; // b bigger or equal to 6 - false
		result = a == b; // a equal to b - false
		result = a != b; // a is not equal to b - true
		result = a > b || a < b; // Logical or - true
		result = 3 < a && a < 6; // Logical and - true
		result = !result; // Logical not - false
	}
}

```
### Logical Operators

- Logical And (`&&`): Evaluates to true, only if both conditions are true
- Logical Or (`||`): Evaluates to true if one of the two or both conditions are true
- Not (`!`): Evaluates to false if the inner condition evaluates to true and vise versa

### Unary Operators

| OPERATOR     | EXPLANATION |
|--------------|:---------:|
| Increment (++) | Increments a given value by 1 |
| Decrement (--) | Decrements a given value by 1 |

## How to work with Strings in Java 

### How to Format a String

You've already seen the usage of the `+` operator to sew strings together or format them in a specific way.

A better way to fromat a string is the `String.format()` method.

``` java 
public class Main {
	public static void main(String[] args) {
		String name = "Farhan";
		int age = 27;
		
		String formmattedString = String.format("My name is %s and I'm %d years old.", name, age);
		System.out.println(formmattedString);
	}
}
```

A chart of the commonly used specifiers are as follows:

| SPECIFIER    | DATA TYPE |
|--------------|:---------:|
| `%b`, `%B`   |  Boolean  |
| `%s`, `%S`   |  String   |
| `%c`, `%C`   |  Unicode Character |
| `%d`         |  Decimal Integer |
| `%f`         |  Floating Point Number |
| `%o`         |  Octal Integers |
| `%x`, `%X`   |  Hexadecimal Numbers|
| `%e`, `%E`   |  Scientific Notations |

### What Are the Different Ways of Inputting and Outputting Data?

`System.out.println()` method

`System.out.print()` method that prints out a given string without appending a newline character to it.

`System.out.printf()` method is kind of combination of the `System.out.print()` and `String.format()` methods.

## Conditional Statements
### `if-else` statements
``` java
if (condition_1) {
	// statements to be executed if condition_1 is true
} else if (condition_2) {
	// statements to be executed if the condition_1 is false and condition_2 is true
} else {
	// statements to be executed if the condition_1 is false and condition_2 is false
}
```
### Ternary Operator
```java
result = (condition) ? expression1 : expression2
```
### `switch-case` statements
```java
switch(expression) {
  case value1:
    // statements to be executed
    break;
  case value2:
    // statements to be executed
    break;

	...

  default:
	// statements to be executed if all cases are not matched; 
}
```

## Iterative Statements
### `for` loop

```java
for (initialization; condition; iteration) {
	// statements to be executed
}
```

### `for-each` loop
There is also a __"for-each"__ loop, which is used exclusively to loop through elements in arrays:

``` java
for (type variable : arrayName) {
	// statements to be executed
}
```

### `while` loop

``` java
while(condition) {
	// statements to be executed
}
```

### `do-while` loop

``` java
do {
	// statements to be executed
} while(conditon);
```

### break and continue
`break` will cause the loop to stop and will go immediately to the next statement after the loop

`continue` will stop the current iteration and will move to the next one. Notice that inside a for loop, it will still run the third section.

### `exit()` method

Syntax of `exit()` in Java

``` java
public static void exit(int status);
```

`System.exit()` method takes status as a parameter, these status codes tell about the status of termination. This status code is an integer value and its meanings are as follows:

- `exit(0`) - Indicates successful termination
- `exit(1)` - Indicates unsuccessful termination
- `exit(-1)` - Indicates unsuccessful termination with Exception
> [!NOTE]
> Any non-zero value as status code indicates unsuccessful termination.

## Package

### Built-in Package

Built-in packages are existing java packages that come along with the JDK (`java.lang`, `java.util`, `java.io`, etc).

### User-defined Package

To define a package in Java, you use the keyword `package`.

``` java
package packageName;
```

For example,

```
└── com
  └── starter
    └── Student.java
```

``` java
package com.starter
```

### Import packages

Java has an `import` statement that allows you to import an entire package.

```java
import package.name.ClassName;   // To import a certain class only
import package.name.*   // To import the whole package
```

Here is an example to import a package using the `import` statement.

```
class MyClass implements java.util.Date {
    //body
}
```

## Array

### Array length

<p align="center"><img src="https://techblogstation.com/wp-content/uploads/2019/11/java-array-length_2.gif" height="100" weight="150"></p>

## String Handling

### Create String using literals vs new keyword

- Creating strings using string literals,

``` java 
String myString = "Java Programming";
```
  - __If the string already exists__, the new string is not created. Instead, the new reference, `myString` points to the already existed string (`Java Programming`).
  - __If the string doesn't exits__, the new string(`Java Programming`) is created.

- Creating strings using the new keyword,

``` java 
String myString = new String("Java Programming");
```
Here, the value of the string is not directly provided. Hence, a new `Jav Programming` string is created even though `"Java Programming"` is already present inside the memory pool.

### Differentiate String == operator and equals() method

We have used the `==` operator and `equals()` method to check if two strings are equal. Here,

- `==` checks if the _reference_ to string objects are equal or not.
- `equals()` checks if the _content_ of the string object are equal.

## Java Modifiers
### Access Modifiers
There are four access modifiers avaliable in Java, used to set access levels for `classes`, `constructor`, `methods`, `variables`

| MODIFIER     | DESCRIPTION |
|--------------|:----------------------------------------------------------------------|
| `private`    | _private_ means that only code within the same class can access the private thing. Keep in mind it means private to the class, not private to the object  |
| `default`    | _default_ access means that only code within the same package as the class with the default thing can access the default thing (package private) |
| `protected`  | _protected_ works just like default (code in the same package has access), EXCEPT it also allows subclasses outside the package to inherit the protected thing  |
| `public`     | _public_ means any code anywhere can access the public thing (class, variable, mehtod, constructor, etc.)  |

- For __classes__, we can use either `public` or `default`
- For __fields__, __methods__, __constructors__, we can use `public`, `private`, `default`, `protected`

> [!NOTE]: 
> - We cannot declare classes and interfaces private in Java. However, the nested classes can be declared private or static.
> - We cannot declare classes or interfaces protected in Java.
> - Methods, variables, classes, and so on are declared public

### Non-access Modifiers
There are five non-access modifiers available in Java, used to achieve many other functionalities.

| MODIFIER     | DESCRIPTION 		      |
|--------------|:-----------------------------|
| `final`   |  Variable values can't be changed once assigned, methods can't be overriden, classes can't be inherited  |
| `static`   |  The member belongs to the class, not to objects of that class  |
| `abstract`   |  If applied to a method - has to be implemented in a subclass, if applied to a class - contains abstract methods  |
| `synchronized`   |  Controls thread access to a block/method  |
| `volatile`   |  The variable value is always read from the main memory, not from a specific thread's memory.  |
| `transient`   |  The member is skipped when serializing an object.  |
| `native`   |    |

- For __classes__, we can use either `final` or `abstract` 
- For __fields__, __methods__, we can use the `final`, `static`, `abstract`, `transient`, `synchronized`, `volatile`
  
## Object Oriented Programming Language
``` java
[class_name] {
    // state or field
    // constructors (No-Arg Constructor, Parameterized Constructor)
    // behavior or method
}
```

### Components in Class
The fields (also known as variables or properties) of a class describe the state of its objects. 

Methods (also known as functions) on the other hand describes the behavior.

### Diference between object and reference
A class in a blue print/user defined datatype in java that describes the behavior/state that the object of its type support.
``` java
public class Student {
	String name = "Krishna";
	int age = 20;
	
	void greet() {
		System.out.println("Hello how are you");
	}
}

public class Example {

	public static void main(String[] args) {
		Student obj = new Student();
	}
}
```
An object is an instance of a class created from it using the new keyword.
Once you create an object of a class, using it you can access he members of the class.

The objects are created in the heap area and, the reference `obj` just points out to the object of the `Student` class in the heap, i.e. it just holds the memory address of the object (in the heap).

And since the String is also an object, under name, a reference points out to the actual String value (“Krishna”).

`Classes`, `interfaces`, `arrays`, `enumerations` and, `annotations` are the in Java are reference types in Java. Reference variables hold the objects/values of reference types in Java

<p align="center"> <img src="https://www.tutorialspoint.com/assets/questions/media/24811/diff_%20between_object%20_and%20_reference.jpg" /></p>

### `this` and `super` keyword

### Constructor
> [!NOTE] 
> A constructor cannot be `abstract` or `static` or `final`
> A constructor be able to have `default` or `public` or `private` or `protected`
> It is important to note that constructors in Java are not inherited. Hence, there is no such thing as constructor overriding in Java. However, We able to call the superclass constructor form the subclass constructor using `super()`. It's a special form of the `super` keyword
> `super()` can be used only inside the `subclass constructor` and must be the fist statement.
> When an object of class is created, it automatically calls the default or no-arg constructor of that class

``` java
// Java programm to ilustrate Constructor Chaining
// Within same class Using this() keyword

class Temp {
	// default constructor 1
	// default constructor will call another constructor
	// using this keyword from same class
	
	Temp() {
		// calls constructor 2
		this(5);
		System.out.println("The Default constructor");
	}
	
	// parameterized constructor 2
	Temp(int x) {
		// calls constructor 3
		this(5, 15);
		System.out.println(x);
	}
	
	// parameterized constructor 3
	Temp(int x, int y) {
		System.out.println(x*y);
	}
	
	public static void main(String[] args) {
		// invokes default constructor first
		new Temp();
	}
}

```

#### Point to remember about constructor in Java class:
- First and most important point is that, name of the constructor should be same as that of class name
- And next important point is, constructor don’t have any return type unlike methods (not even void)
- Every concrete class and abstract class has a constructor
- Constructor in interfaces is not allowed
- It can have all Java statements and logic but shouldn’t return any value
- Constructor can have zero arguments which are called default constructor (or no-arg constructor)
- Constructor can have one or more input parameters which are called as parameterized constructor
- If we don’t specify any constructor explicitly then compiler inserts a default no-arg constructor during compilation
- But when we declare any constructor explicitly either it is no-arg constructor or parameterized constructor, then compiler doesn’t inserts default constructor
- this() is used to invoke another constructor in the same class, if present must be the first statement of the constructor. There cannot be two this() statement in the constructor call
- Constructor cannot be inherited therefore it can’t be overridden
- _super()_ is used to invoke another constructor in super class, if present must be the first statement of the constructor
- But both this() and super() cannot exists at the same time because both cannot be first statement of the constructor which results compilation failure
- A class can have more than one constructor i.e.; Constructor Overloading
- All four access modifier i.e.; private, default, protected, public are allowed (no restriction on access modifiers)
- Private constructor are used for singleton design pattern
- Non-access modifier like static, final, synchronized, abstract, strictfp, transient, volatile are not allowed

### Abstract Class
### Interface
- Like __abstract classes__, interfaces __cannot__ be used to create objects (in the example above, it is not possible to create an "Animal" object in the MyMainClass)
- Interface methods do not have a body - the body is provided by the "implement" class
- On implementation of an interface, you must override all of its methods
- Interface methods are by default `abstract` and `public`
- Interface fields are by default `public static final`
```java
interface Language {
  // by default public static final
  String type = "Programming Language";
  
  // by default public abstract
  void getName();
}
```
- An interface cannot contain a constructor (as it cannot be used to create objects)
- Java does not support "multiple inheritance" (a class can only inherit from one superclass). However, it can be achieved with interfaces, because the class can implement multiple interfaces.

```java
interface Polygon {
    void getArea();

    // default method
    default void getPerimeter(int... sides) {
        int perimeter  = 0;
        for(int side : sides){
            perimeter  += side;
        }
        System.out.println("Perimeter: " + perimeter );
    }

    default void getSides() {
        System.out.println("I can get sides of a polygon.");
    }
}


class Triangle implements Polygon {
    private int a, b, c;
    private double s, area;
    Triangle(int a, int b, int c) {
        this.a = a;
        this.b =b;
        this.c = c;
        s = 0;
    }

    @Override
    public void getArea() {
        s = (double) (a + b + c)/2;
        area = Math.sqrt(s*(s-a)*(s-b)*(s-c));
        System.out.println("Area: " + area);
    }

    @Override
    public void getPerimeter(int... sides) {
        Polygon.super.getPerimeter(sides);
    }

    @Override
    public void getSides() {
        Polygon.super.getSides();
    }
}

// implement the interface
class Rectangle implements Polygon {
    @Override
    public void getArea() {
        int length = 6;
        int breadth = 5;
        int area = length*breadth;
        System.out.println("The eare of the rectangle is " + area);
    }

    @Override
    public void getSides() {
        System.out.println("I have 4 sides.");
    }
}

// implement the interface
class Square implements Polygon {
    @Override
    public void getArea() {
        int length = 5;
        int area = length * length;
        System.out.println("The area of the square is " + area);
    }
}

public class Main {
    public static void main(String[] args) {

        // create an object of Rectangle
        Rectangle rectangle = new Rectangle();
        rectangle.getArea();
        rectangle.getSides();

        // create an object of Square
        Square square = new Square();
        square.getArea();
        square.getSides();

        // create an object of Triangle
        Triangle triangle = new Triangle(2, 3, 4);
        triangle.getArea();
        triangle.getPerimeter(2, 3, 4);
    }
}
```
> __Note__: 
> All the methods inside an interface are implicitly `public` and all fields are implicitly `public static final`.

### Overriding and Overloading

#### Method Overriding and Method Overloading

<p align="center"><img src="https://miro.medium.com/max/1400/0*Jii_jcKX3sOCzaIS.png"/></p>

- Definitions

  - _Overloading_: occurs when two or more methods in one class have the same method name but different parameters.

  - _Overriding_: means having two methods with the same method name and parameters (i.e., method signature). One of the methods is in the parent class and the other is in the child class. Overriding allows a child class to provide a specific implementation of a method that is already provided its parent class.

> __Note__: 
> We cannot override the methods declared as `final` and `static`
> We should always override `abstract methods` of superclass

## Java Enums
An `enum` is a special "class" the represents angroup of __constants__ (unchangeable variables, like `final` variables). All enum constant is always `public`, `static`, `final` by default

To create an `enum`, use the `enum` keyword (instead of class or interface), and separate the constants with a comma. Note the they should be in uppercase letters

You can access `enum` constants with the __dot__ syntax:

``` java 
enum Level {
LOW,
MEDIUM,
HIGH
}

public class Main { 
  public static void main(String[] args) { 
    Level myVar = Level.MEDIUM; 
    System.out.println(myVar); 
  } 
}
```

## Exception Handling

### `throw` and `throws` keywords

In Java, exceptions can be categorized into two types:

- __Unchecked Exceptions__: They are not checked at compile-time but at run-time.For example: `ArithmeticException`, `NullPointerException`, `ArrayIndexOutOfBoundsException`, exceptions under `Error` class, etc.

- __Checked Exceptions__: They are checked at compile-time. For example, `IOException`, `InterruptedException`, etc.

For example,

``` java
try {
    throw new NullPointerException();
}
catch (NullPointerException e) {
    System.out.println(e);
}

try {
    throw new IOException();
}
catch (IOException e) {
    e.printStackTrace();
}
System.exit(0);
```

- Calling `println(e)`:

```
java.lang.NullPointerException
```

- Calling `e.printStackTrace()`:

```
java.io.IOException
    at package.Test.main(Test.java:74)
```

## Collection

### Methods of Collection

The Collection interface includes various methods that can be used to perform different operations on objects. These methods are available in all its subinterfaces.

- `add()` - inserts the specified element to the collection
- `size()` - returns the size of the collection
- `remove()` - removes the specified element from the collection
- `iterator()` - returns an iterator to access elements of the collection
- `addAll()` - adds all the elements of a specified collection to the collection
- `removeAll()` - removes all the elements of the specified collection from the collection
- `clear()` - removes all the elements of the collection

### List Interface

``` java

List<Data-Type>linkedlist = new LinkedList<Data-Type>();   
    
List<Data-Type>arraylist = new ArrayList<Data-Type>();
    
List<Data-Type>vector = new Vector<Data-Type>();

List<Data-Type>stack = new Stack<Data-Type>();

```

#### Methods of List

Some of the commonly used methods of the Collection interface that's also available in the List interface are:

- `add()` - adds an element to a list
- `addAll()` - adds all elements of one list to another
- `get()` - helps to randomly access elements from lists
- `iterator()` - returns iterator object that can be used to sequentially access elements of lists
- `set()` - changes elements of lists
- `remove()` - removes an element from the list
- `removeAll()` - removes all the elements from the list
- `clear()` - removes all the elements from the list (more efficient than removeAll())
- `size()` - returns the length of lists
- `toArray()` - converts a list into an array
- `contains()` - returns true if a list contains specified element

### Queue Interface

```java
Queue<Data-Type> pq = new PriorityQueue<Data-Type>(); 
Queue<Data-Type> ad = new ArrayDeque<Data-Type>(); 
```

```java
Deque<Data-Type> ad = new ArrayDeque<Data-Type>();
```

### Set Interface

``` java

Set<Data-Type> hs = new HashSet<Data-Type>();  

Set<Data-Type> lhs = new LinkedHashSet<Data-Type>();  

Set<Data-Type> ts = new TreeSet<Data-Type>();  

```

```java
SortedSet<Data-Type> ts = new TreeSet<Data-Type>();  
```

### Map Interface

## Rules for writing a Java Program

- Java always uses higher CamelCase for writing class names and lower camelCase for writing method names. Variable names should always start with either an alphabet or an underscore(_). It can contain digits but not at starting. Use meaningful names for variables.

- Java is case-sensitive. ‘Hello’ is not the same as ‘heLLo’.

- Use indentation for structuring your program. The body of a class definition and method definition should be indented to increase the readability of your program.

- Every executable statement in Java should terminate with a semicolon.

## Stream API

### Introduction of Streams in Java

Consider Java stream as a pipeline that consists of a stream source followed by zero or more intermediate operations and a terminal operation. Stream is not a collection or a data structure where we can store data.

- `Stream source` is a Stream instance that contains the initial data.
- `Intermediate operations` are used to perform actions on stream data and return another stream as output.
- `Terminal operations` produce the result of the stream after all the intermediate operations are applied.

Basically we pass input to the stream and apply zero or more intermediate operations to manipulate the data and finally, the result can be collected using a terminal operation.

``` java
Stream.of(1, 2, 3, 4, 5)          	// Stream source
    .filter(x -> x % 2 == 0)      	// Intermediate operation
    .collect(Collectors.toList()) 	// Terminal operation
```

```java
public class Main{
    public static void main(String[] args) {
        int[] arrayToConverted = {104, 58, 86, 85, 45};
        Integer[] resultArray = Arrays.stream(arrayToConverted)
                .boxed()
                .toArray(Integer[]::new);
        System.out.println(arrayToConverted.getClass());
        System.out.println(resultArray.getClass());
        System.out.println(Arrays.toString(resultArray));
        System.out.println(Arrays.toString(arrayToConverted));

    }
}
```

## Generic

- `T` - Type (Used in Map)
- `E` - Element(Used extensively by the Java Collections Framework)
- `K` - Key (Used in Map)
- `N` - Number
- `V` - Value (Used in Map)
- `S`,`U`,`V` - 2nd, 3rd, 4th types

### Generic Class

Syntax of Generic Class

``` java
class GenericClass<T> {...}
```

### Generic Method

Syntax of Generic Method

``` java
public <T> void genericMethod(T data) {...}
```

### Example

``` java
package com.tutorial.test;

import java.util.ArrayList;
import java.util.Collection;
import java.util.List;

class Shoe {}
class IPhone{}

interface Fruit {}

class Apple implements Fruit{}
class Banana implements Fruit{}
class GrannySmith extends Apple{}

class FruitHelper {

    public void eatAll(Collection<? extends Fruit> fruits) {}

    public void addApple(Collection<? super Apple> apples) {}
}

public class Main {
    public static void main(String[] args) {
        FruitHelper fruitHelper = new FruitHelper() ;
        List<Fruit> fruits = new ArrayList<>();

        fruits.add(new Apple()); // Allowed, as Apple is a Fruit
        fruits.add(new Banana()); // Allowed, as Banana is a Fruit
        fruitHelper.addApple(fruits); // Allowed, as "Fruit super Apple"
        fruitHelper.eatAll(fruits); // Allowed

        Collection<Banana> bananas = new ArrayList<>();
        bananas.add(new Banana()); // Allowed
//        fruitHelper.addApple(bananas); // Compile error: may only contain Bananas!
        fruitHelper.eatAll(bananas); // Allowed, as all Bananas are Fruits

        Collection<Apple> apples = new ArrayList<>();
        fruitHelper.addApple(apples); // Allowed
        apples.add(new GrannySmith()); // Allowed, as this is an Apple
        fruitHelper.eatAll(apples); // Allowed, as all Apples are Fruits.

        Collection<GrannySmith> grannySmithApples = new ArrayList<>();
//        fruitHelper.addApple(grannySmithApples); //Compile error: Not allowed.
        // GrannySmith is not a supertype of Apple
        apples.add(new GrannySmith()); //Still allowed, GrannySmith is an Apple
        fruitHelper.eatAll(grannySmithApples);//Still allowed, GrannySmith is a Fruit

        Collection<Object> objects = new ArrayList<>();
        fruitHelper.addApple(objects); // Allowed, as Object super Apple
        objects.add(new Shoe()); // Not a fruit
        objects.add(new IPhone()); // Not a fruit
        //fruitHelper.eatAll(objects); // Compile error: may contain a Shoe, too!
    }
}
```

## Reader/Writer

## Multithreading
- Java runtime environment runs as a single process which contains different classes and programs as processes.
- Java provides two ways to create a thread programmatically:
  	- Implementing the __java.lang.Runnable__ interface
  	- Extending the __java.lang.Thread__ class

### Implementing Runnable interface
To make a class runnable, we can implement java.lang.Runnable interface and provide implementation in `public void run()` method. To use this class as Thread, we need to created a Thread object by passing object of this runnable class and then call `start()` method to execute the `run()` method in a separate thread.

### Extending Thread class
We can extend __java.lang.Thread__ class to create our own java thread class and override `run()` method. Then we can create it's object and call `start()` method
to execute our custom Java thread class run method.

### Runnable vs Thread
If your class provides more functionality rather than just running as Thread, you should implement Runnable interface to provide a way to run it as Thread. If your class only goal is to run as Thread, you can extend Thread class. Implementing Runnable is preferred because Java supports implementing multiple interfaces. If you extend Thread class, you can't extend any other classes.


## References
- [Start Here](https://www.baeldung.com/start-here)
- [Java Developer Roadmap](https://dev.to/rameshfadatare/java-developer-road-map-2022-3mg5)
- [Mooc.fi Java Course](https://java-programming.mooc.fi/)
- [Learn Java](https://dev.java/learn/)
- [Core Java Tutorial with Examples](https://java2blog.com/core-java-tutorial-for-beginners-experienced/)
- [Introduction to Java](https://www.koderhq.com/tutorial/java/)
- [Java Programming Cheatsheet](https://javatechonline.com/static-keyword-in-java/)
- [Learn Java Programming](https://www.programiz.com/java-programming)
- [Learn Java Online](https://www.learnjavaonline.org/)
- [Java Tutorial](https://javabeginnerstutorial.com/core-java-tutorial/)
- [Learn Java Programming with Examples](https://beginnersbook.com/java-tutorial-for-beginners-with-examples/)
- [Core Java Tutorial](https://www.journaldev.com/7153/core-java-tutorial)
- [Execution Process of Java Program in Detail](https://simplesnippets.tech/execution-process-of-java-program-in-detail-working-of-just-it-time-compiler-jit-in-detail/)
- [The Definitive Guide to Java Backend Developer Career Path](https://www.devoxify.com/posts/the-definitive-guide-to-java-backend-developer-career-path/)
- [Java Programming](http://www.btechsmartclass.com/java/java-index.html)
- [Java Tutorial](https://howtodoinjava.com/java/basics/java-tutorial/#6-learning-java)
- [Java Programming Library](https://www.programiz.com/java-programming/library)
- [Access modifier](https://www.scientecheasy.com/2020/06/access-modifiers-in-java.html/)
- [Point to remember about constructor in Java class](https://www.benchresources.net/java-constructor-with-example/)
