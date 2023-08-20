[variables](#variables) | [Methods](#methods) | [Data Types in Java](data-types-in-java) | [primitive](#there-are-8-types-of-primitive-data-types) | [Non-primitive](#non-primitive-data-types) | [Arithmetic Operators and there Precedence ](#arithmetic-operators-and-there-precedence-in-java) | [Convert Decimal &#8644; Binary](#decimal-to-binary-and-binary-to-decimal) | [Chars](#how-char-is-going-to-store-in-memory) | [Typecasting](#typecasting) | [Some scanner options](#some-scanner-options) | [Relational Operators](#relational-logical-and-unary-operators) |[Assignment Operators](#relational-logical-and-unary-operators) |  [Arithmetic Operators](#relational-logical-and-unary-operators) | [Logical Operators](#relational-logical-and-unary-operators) |  [Unary Operators](#relational-logical-and-unary-operators) | [ Bitwise Operators](#relational-logical-and-unary-operators) | [Scope and Lifetime](#scope-and-lifetime) | [Pass by value](#pass-by-value) | [Break and Continue keyword](#break-and-continue)

># variables
In Java, Variables are the data containers that save the data values during Java program execution. Every Variable in Java is assigned a data type that designates the type and quantity of value it can hold. A variable is the name of a reserved area allocated in memory. In other words, it is a name of the memory location. It is a combination of "vary + able" which means its value can be changed.

while declaring a variable, we need to take care of two things that are:

**datatype:** Type of data that can be stored in this variable.
**data_name:** Name was given to the variable

```java
int let =50;//int is data type and Here let is variable
```

**Types of Variables**
There are three types of variables in Java:

* local variable
* instance variable
* static variable

1. ***Local Variable:***

A variable defined within a block or method or constructor is called a local variable.

*Example:*
In programming, local variables are like notes you create inside a method or a specific part of your code. They hold data that's needed temporarily for that part of the code. Once the method or code block is finished, the local variables disappear, just like your sticky notes after you're done with the task.

Imagine you're baking cookies. While you're mixing the ingredients, you might use a "mixing bowl" to keep track of the current mixture. That mixing bowl is like a local variable. It's relevant only while you're mixing the ingredients, and you don't need it once the cookies are baked.

*  These variables are created when the block is entered, or the function is called and destroyed after exiting from the block or when the call returns from the function.
* The scope of these variables exists only within the block in which the variables are declared, i.e., we can access these variables only within that block.
* Initialization of the local variable is mandatory before using it in the defined scope.
* They don't have default values like instance or class variables.

```java
void calculate() {
    int result = 10; // Local variable
    System.out.println(result);
}
```

2. ***Instance Variable (also called Fields):***

Instance variables are non-static variables and are declared in a class outside of any method, constructor, or block.

*Example:*
Imagine you have a personal notebook where you jot down important things about yourself. Each person has their own notebook, and what you write in your notebook is unique to you.

In programming, instance variables are like those personal notebooks. They belong to each individual object (instance) of a class. Each object can have its own set of instance variables, and the values in these variables can be different for each object.

Consider a class named Person. Each person has their own name and age, stored in instance variables. So, if you have a class instance for yourself and another for a friend, the name and age instance variables will hold different values for each of you.

* An instance variable is declared within a class but outside any method, these variables are created when an object of the class is created and destroyed when the object is destroyed.
* Unlike local variables, we may use access specifiers for instance variables. If we do not specify any access specifier, then the default access specifier will be used.
* We initialize instance variables using constructors while creating an object. We can also use instance blocks to initialize the instance variables.
* Each instance (object) of the class has its own copy of the instance variable.
* Instance variables are created when an object is instantiated/by creating objects.
* Initialization of an instance variable is not mandatory.They have default values (0, null, false) if not explicitly initialized.Its default value is dependent on the data type of variable. For String it is null, for float it is 0.0f, for int it is 0, for Wrapper classes like Integer it is null, etc.

```java
class Person {
    String name;    // Instance variable
    int age;        // Instance variable
}
```

3. ***Static Variable (also called Class Variable):***

Static variables are also known as **class variables**.

* These variables are declared similarly to instance variables. The difference is that static variables are declared using the static keyword within a class outside of any method, constructor, or block.

*Example:*

Think of static variables as a shared whiteboard that everyone in a class can write on. Any updates you make on the whiteboard are visible to everyone who looks at it.

In programming, static variables are like shared information that's common to all instances of a class. These variables are shared among all objects of the class, and changes made to them are visible to all instances.


Imagine you're in a classroom, and there's a "class count" board that keeps track of the total number of students. Every time a student enters or leaves the class, the count changes. This "class count" board is like a static variable. All students see the same count, and any updates to it are shared among everyone.

* Unlike instance variables, we can only have one copy of a static variable per class, irrespective of how many objects we create. Static variables are shared among all instances of the class.
* Static variables are created at the start of program execution(when the class is loaded into memory) and destroyed automatically when execution ends(i.e. exist for the entire program's lifetime).
* Initialization of a static variable is not mandatory. Its default value is dependent on the data type of variable. For String it is null, for float it is 0.0f, for int it is 0, for Wrapper classes like Integer it is null, etc.
* If we access a static variable like an instance variable (through an object), the compiler will show a warning message, which won’t halt the program. The compiler will replace the object name with the class name automatically.
* If we access a static variable without the class name, the compiler will automatically append the class name. But for accessing the static variable of a different class, we must mention the class name as 2 different classes might have a static variable with the same name.
* Static variables cannot be declared locally inside an instance method.
* Static blocks can be used to initialize static variables.


```java
class MathUtility {
    static final double PI = 3.14159; // Static variable
    static int counter = 0;          // Static variable
}
```

##### Differences Between the Instance Variables and the Static Variables

* Each object will have its own copy of an instance variable, whereas we can only have one copy of a static variable per class, irrespective of how many objects we create. Thus, static variables are good for memory management.
* Changes made in an instance variable using one object will not be reflected in other objects as each object has its own copy of the instance variable. In the case of a static variable, changes will be reflected in other objects as static variables are common to all objects of a class.
* We can access instance variables through object references, and static variables can be accessed directly using the class name.
* Instance variables are created when an object is created with the use of the keyword ‘new’ and destroyed when the object is destroyed. Static variables are created when the program starts and destroyed when the program stops.

***In summary:***

* **Local variables** are used within methods or blocks and have limited scope.Local variables are temporary notes specific to a part of your code.
* **Instance variables** are associated with an instance (object) of a class and each instance has its own copy.Instance variables are like personal notebooks, unique to each object.
* **Static variables** are shared among all instances of a class and are declared using the static keyword.Static variables are shared information that's the same for all objects of a class

---
> # Methods

1. ***Local Method:***

Imagine you're building a sandcastle on the beach. You have a little bucket that you use to collect sand. The bucket is like a "local" tool because you only use it right where you're building the sandcastle.
In Java, a local method is like a set of instructions that only make sense in one particular part of your code. These instructions use tools (variables) that are only available right there. Once you're done building your sandcastle (or your code finishes running the method), those instructions and tools go away.

2. ***Instance Method:***

Think of a family where everyone has their own lunchbox. Each lunchbox holds a unique meal for each person.
In Java, an instance method is like a set of instructions that's specific to each "person" (or object) created from a class. Just like each family member has their own lunchbox with a special meal, each object has its own set of instructions that can work with its own unique data. These instructions define how each object can do things on its own.

3. ***Static Method:***

Imagine you're at a school event, and there's a microphone set up for everyone to use. You can step up to the microphone and share your thoughts with everyone in the room.
In Java, a static method is like something everyone can use without needing their own copy. It's like a set of instructions that's not tied to any specific "person" (object). Just like anyone can use the microphone, any part of the code can use a static method to do something without creating an "object."


lets see an example
```java
// Class definition
class Car {
    // Instance variables
    String brand;
    String model;

    // Constructor
    Car(String brand, String model) {
        this.brand = brand;
        this.model = model;
    }

    // Instance method
    void startEngine() {
        System.out.println("Starting the engine of " + brand + " " + model);
    }

    // Static variable
    static int numberOfCars = 0;

    // Static method
    static void increaseCarCount() {
        numberOfCars++;
    }

    // Local method
    void accelerate() {
        int speed = 50; // Local variable
        System.out.println("Accelerating " + brand + " " + model + " to " + speed + " km/h");
    }
}

public class Main {
    public static void main(String[] args) {
        // Creating objects
        Car car1 = new Car("Toyota", "Corolla");
        Car car2 = new Car("Honda", "Civic");

        // Accessing instance variables
        System.out.println("Car 1: " + car1.brand + " " + car1.model);
        System.out.println("Car 2: " + car2.brand + " " + car2.model);

        // Accessing instance methods
        car1.startEngine();
        car2.startEngine();

        // Accessing static variable and method
        Car.increaseCarCount();
        System.out.println("Total cars: " + Car.numberOfCars);

        // Calling local method
        car1.accelerate();
        car2.accelerate();
    }
}
```
**In this example:**

* The Car class defines instance variables (brand and model), an instance method (startEngine()), a static variable (numberOfCars), and a static method (increaseCarCount()).
* The Car class constructor is used to initialize instance variables when creating objects.
* In the Main class, we create two Car objects (car1 and car2), each with its own brand and model.
* We access instance variables using object references (car1.brand).
* We call instance methods on objects (car1.startEngine()).
* We access static variables and methods using the class name (Car.increaseCarCount()).
* The local method accelerate() uses a local variable speed.

 *if you remove the static keyword from the increaseCarCount() method, it will no longer work correctly, and you'll encounter a compilation error. This is because the numberOfCars variable is a static variable, which means it belongs to the class itself rather than any specific instance of the class.
Non-static (instance) methods can't directly access or modify static variables because static variables are shared among all instances of the class. When you try to access a static variable from a non-static method without specifying an instance, the compiler doesn't know which instance's static variable to access.*

**In summary:**

* Local methods are like specific instructions used in a particular part of your code, using tools (variables) that are only available there.
* Instance methods are instructions that each "person" (object) in your program can use, tailored to their unique data.
* Static methods are instructions that anyone can use without needing their own copy, just like sharing a microphone.

---
># Data Types in Java

Think of data types as different boxes that can hold different kinds of things. Just like you might have a box for toys, another for clothes, and yet another for books, in programming, we have data types specify the different sizes and values that can be stored in the variable/different types of information.***Java is a statically-typed programming language. It means, all variables must be declared before its use. That is why we need to declare variable's type and name.*** Picture this: before you start playing with your toys, you need to tell someone what kind of toys you have. Similarly, in Java, you need to tell the computer what type of information you're going to store in a box (variable) before you start using it. This is called "declaring" the variable. Statically-typed means you need to declare the type of your variables before you can use them, just like you need to announce what kind of toys you have before you can play with them.

*There are two types of data types in Java:*

**Primitive data types:** Imagine you have some basic kinds of things that can fit into small boxes. For example, you can put a "yes" or "no" (boolean), a single letter (char), or small numbers (byte, short, int) into these boxes. Some boxes can even hold numbers with a decimal point (float, double). These boxes are like the primitive data types, and they're used to store simple and common types of information.The primitive data types include boolean, char, byte, short, int, long, float and double.

**Non-primitive data types:** imagine you have more complex things that can't fit into a single box. For instance, you might have a special box that holds a bunch of toys, or another that holds a stack of books. In programming, non-primitive data types are like these special boxes. They can hold more complex things, like groups of related information (classes), rules for how things should be done (interfaces), or collections of similar things (arrays).The non-primitive data types include Classes, Interfaces, and Arrays.

#### There are 8 types of primitive data types:

* boolean: Holds either true or false, representing a binary choice.
* char: Stores a single character and is denoted using single quotes, like 'A'.'\u0000' is Unicode character representation of "null" character which is default value.
* byte: Stores small integer values within the range of -128 to 127.
* short: Holds small integer values from -32,768 to 32,767.
* int: Used for whole numbers within a wide range.
* long: Used for large whole numbers, with a larger range than int.
* float: Stores floating-point numbers with approximately 6-7 decimal digits of precision.
* double: Holds floating-point numbers with approximately 15 decimal digits of precision.
#### 1 byte = 8 bits  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; _ _ _ _ _ _ _ _
|Data Type|	Default Value|	Default size|value-range|
|---------|--------------|-------------|-----------|
|boolean|false|Not specified|true/false|
|char|'\u0000'|2 byte|0 to 65,535|
|byte|0|1 byte|-(2<sup>7</sup>) to (2<sup>7</sup>-1)|
|short|0|2 byte|-(2<sup>15</sup>) to (2<sup>15</sup>-1)|
|int|0|4 byte|-(2<sup>31</sup>) to (2<sup>31</sup> -1)|
|long|0L|8 byte|-(2<sup>63</sup>) to (2<sup>63</sup> -1)|
|float|0.0f|4 byte|Approximately ±3.40282347E+38F (6-7 decimal digits)|
|double|0.0d|8 byte|Approximately ±1.79769313486231570E+308 (15 decimal digits)|
___

#### Non-Primitive Data Types:
Non-primitive data types are like containers that can hold more complex and organized information compared to the simple data types we discussed earlier. They are like special boxes that can hold not just one thing, but a whole bunch of things or even a set of rules.

**Classes:** Think of a class like a blueprint for creating objects. It's like a recipe that tells you how to make something. For example, you might have a class called "Car" that describes how to make cars. Each car you create from that class is like a real car based on the blueprint.

**Interfaces:** An interface is like a contract that different classes agree to follow. Imagine you're a teacher and you have a lesson plan that you follow in different classes. The lesson plan is the interface, and each class agrees to teach according to that plan. This helps ensure consistency even though the actual teaching methods might vary.

**Arrays:** An array is like a row of boxes where you can put related items. Imagine you have a row of lunchboxes, and each box holds a different type of food. In programming, an array lets you store multiple items of the same type in an organized way, making it easier to manage and work with groups of data.

***non-primitive data types don't have the same kind of fixed, predefined minimum values as primitive data types. Their behavior and initial values depend on how they are defined and used in your program.***

int data type occupies 4 bytes of memory. So, if you have an array of integers with a length of 10 ---> Array length × Size of each element = Total memory required
10 × 4 bytes = 40 bytes.
An array of integers with a length of 10 would indeed require 40 bytes of memory.

---
>## Arithmetic Operators and there Precedence in Java
Operator in Java is a symbol that is used to perform operations. For example: +, -, *, / etc.

There are many types of operators in Java which are given below:
* Unary Operator,
* Arithmetic Operator,
* Shift Operator,
* Relational Operator,
* Bitwise Operator,
* Logical Operator,
* Ternary Operator and
* Assignment Operator.


|Operator Type|	Category|	Precedence|
|-------------|-----------|-------------|
|Unary	|postfix	|expr++ expr--|
|        |prefix	|++expr --expr +expr -expr ~ !|
|Arithmetic	|multiplicative|* &nbsp; / &nbsp;  %|
|           |additive|+ &nbsp; -|
|Shift|shift|<< >> >>>|
|Relational|comparison|< >  &nbsp; <=  &nbsp; >=  &nbsp; instanceof|
|          |equality|==  &nbsp; !=|
|Bitwise|bitwise AND|&|
||bitwise exclusive OR|<sup>|</sup>
||bitwise inclusive |OR|`|`|
|Logical|	logical AND|	&&|
||logical OR|`||`|
|Ternary|ternary|	?  &nbsp; :|
|Assignment|assignment|= &nbsp; += &nbsp; -= &nbsp; *= &nbsp; /= &nbsp; %= &nbsp; &= &nbsp; <sup>=</sup> &nbsp; `|=` &nbsp; <<= &nbsp; >>= &nbsp; >>>=|

---
* **double a = 10 / 30; is 0.0**

 bcz it start from right side and hence both the operants 10 and 30 are of type int ,and at time of this calculation both are int ,hence answer would be int, then it store in double hence value is 0.0 not 0.3

* **int c = 3 + 2 / 5;**

ans is 3 not 1, bcz bodmas , divide has more presidence
* **inc c = 3 * 2 / 5;**

ans is 1, bcs * / % have same presidence, and whens have same presidence then operation goes from left to right direction

* **int c = 10/(2*3);**

   bracket have more presidence so operation inside the bracket will happen first.
---

>## Decimal to Binary and Binary to Decimal

* *20 in binary: this is for +ve number converson* taking 6 Bits as example _ _ _ _ _ _

|2|20||
|-|--|-|
|2|10|0|
|2|5|0|
|2|2|1|
||1|0|

Reading from bottom to top (0 1 0 1 0 0), this is the required result, which will ultimately result in decimal form.
(1x2<sup>4</sup> + 0x2<sup>3</sup> + 1x2<sup>2</sup> + 0x2<sup>1</sup> + 0x2<sup>0</sup>) = (16 + 0 + 4 + 0 + 0) = 20

* *-20 in binary*

-ve numbers are actully stored in its 2's complement form 
1. Convert 20 to binary: 20 = 010100
2. Complement each bit, which means changing 0s to 1s and 1s to 0s. So, 010100 becomes 101011.
3. Add 1: 101100
4. this 101100 is -20

the binary representation 101100 is indeed the two's complement representation of -20.

* **now 101100 to decimal**

When you have a binary number, start by reading from its sign bit, which is the leftmost bit. If this bit is 1, it indicates that the number is negative. As this is a negative number, it is actually stored in its two's complement form. To retrieve the original number, you need to take its two's complement again.

So, for the binary number 101100, its two's complement is 010011. Adding 1 to 010011 results in 010100, which is the original number. When you convert this binary representation to decimal, you get 20. Since the initial sign bit is 1, indicating a negative number, you put a negative sign in front of 20, resulting in -20, the correct value."

---

> ### How char is going to store in memory

Chars are 2 bytes long (16 bits). Let's consider the example:
```java
char ch = 'a';
```
When the character 'a' is assigned to the variable ch, it's not directly stored in memory. Instead, the ASCII value of 'a' in its binary form is stored in memory. The ASCII value of 'a' is 97, so the binary representation of 97 is what's actually stored in memory.

0 is a character as well, with ascii value 48.

```java
System.out.print('a' + 3);// is 100.
```
So, how is 100 being calculated? When you try to add characters, the system deals with their ASCII values. ***(Deep down, whenever you deal with characters, the system is actually working with their ASCII values. anywhere not just only here)*** The ASCII value of 'a' is 97, and when you add 3 to 97, you get 100.

---
># Typecasting

* **Implicit Conversion (Widening Conversion):**

Think of it like upgrading your phone. If you have an old phone with a small screen and decide to get a new phone with a bigger screen, it's an automatic upgrade. No data is lost, and everything fits nicely on the larger screen.

* **Explicit Conversion (Narrowing Conversion):**

Imagine you have a big bucket of water, and you want to pour it into a smaller cup. You have to do this carefully, knowing that some water might spill or get left behind. Explicit conversion is like pouring water from a bigger container to a smaller one. You need to do it manually, and there's a chance of losing some water in the process.

*In programming terms, implicit conversion is like a safe, automatic upgrade, while explicit conversion is a manual process that requires caution and may involve losing some data.*

```java
char ch = 'a';
int i = ch;//no error
System.out.print(i);// is 97.
```
[see Char](#how-char-is-going-to-store-in-memory),  Since a char occupies 2 bytes and an int occupies 4 bytes, any number that can be stored in 2 bytes can easily be stored in 4 bytes.

**However,**

```java
char ch = 'a';
int i = ch;
ch = i;//show an error, type does't match
System.out.print(i);// is 97.
```
Although we are storing 97 from i to ch, we can't store 4 bytes into 2 bytes; the compiler doesn't allow it.

If you want to store an int into a char, you can use explicit conversion:

```java
char ch = 'a';
int i = ch;
ch = (char)i;//show an error, type does't match
System.out.print(i);// is 97.
```
There can be data loss when converting from 4 bytes to 2 bytes. If you intend to do so system says lets do that.

```java
int i = 'a' + 3;//this is correct no error.
char ch = 'a' + 3;//this is incorrect, bcz 100 is int and you can't store it into char.
```

similarly for int & small , int & byte and small & byte.

---
```java
float f = 10.3;//throw an error
```
*Let's break it down step by step. The entire line doesn't execute all at once; it's processed in stages. First, the right side of the assignment will execute. In this case, 10.3 will be stored in a temporary memory location of type double (since it's a decimal number). This temporary memory occupies 8 bytes. On the other hand, a float occupies only 4 bytes of memory. Now, the content of this 8-byte memory is supposed to be stored or copied into the 4-byte memory allocated for the float. This is where the error occurs. You're trying to fit something big into something small. The double value 10.3 is too large to fit perfectly into the float variable f, which is why Java raises an error.*

---

```java
System.out.print(4 + 4);// is 8 (int+int)
System.out.print(4 + 4.5);// is 8.5, (int + double)
System.out.print(4.1 + 4.4);// is 8.5, (double + double)
System.out.print(2/5);// is 0. (int/int)
System.out.print((double)2/5);// is 0.4 ,convert 2 explicit to double
System.out.print(2.0/5);// is 0.4 (double/int)
```
1. Both operands are integers, so the result is also an integer, which is 8.
2. When an integer (4) is added to a decimal number (4.5), the integer is temporarily promoted to a double (4.0) before the addition. The result is a double: 8.5.
3. Two decimal numbers are added (4.1 and 4.4), resulting in the sum 8.5.
4. Integer division (2/5) results in an integer quotient. The decimal part is truncated, and you get 0.

 When different data types are involved in calculations, Java automatically converts them to a common data type as needed.
 ___

 ># Some scanner options
Some commonly used Scanner class methods are as follows:
|METHOD |DESCRIPTION|
|-|-|
|s.next() |It returns the next token from the Scanner.|
|s.nextLine()|It moves the Scanner position to the next line and returns the value as a string.|
|s.nextByte()|It scans the next token as a byte.|
|s.nextShort()|It scans the next token as a short value.|
|s.nextInt()|It scans the next token as an int value.|
|s.nextLong()|It scans the next token as a long value.|
|s.nextFloat()|It scans the next token as a float value.|
|s.nextDouble()|It scans the next token as a double value.|
----

>## Relational, Logical and Unary Operators


***1. Arithmetic Operators***
Arithmetic operators are used to perform common mathematical operations.


|Operator|	Name| Description	|Example|
|-|-|-|-|
|+	|Addition|	Adds together two values	|x + y|
|-	|Subtraction|	Subtracts one value from another|	x - y|
|*	|Multiplication|	Multiplies two values	|x * y|
|/	|Division	|Divides one value by another	|x / y|
|%	|Modulus	|Returns the division remainder	|x % y|
|++	|Increment	|Increases the value of a variable by 1	|++x|
|--|	Decrement|	Decreases the value of a variable by 1	|--x|

  * *postIncrement and postDecrement*
    x++ means current value of x will use then it will increment
    x-- means first use then decrease
  * *preIncrement and preDecrement*
    ++x means first increase then use,
    --x first decrease then use

***2. relational Operators***

```java
int a = 10;
int b = 20;
System.out.print(a > b);// false
System.out.print(a > b);// false
System.out.print(a < b);// true
System.out.print(a == a);// true
System.out.print(a == b);// false, if we think to compair a = b , this is incorrect bcz here we are assigning b's value to a.
System.out.print(a != b);// true
System.out.print(a >= b);// false
System.out.print(a <= b);// true
```

***3. Logical Operators***
   * AND Operator ( && ) – if( a && b ) [if true execute else don’t]
   * OR Operator ( || ) – if( a || b) [if one of them is true to execute else don’t]
   * NOT Operator ( ! ) – !(a<b) [returns false if a is smaller than b]

***4. Unary Oprators***

Unary operators are operators in Java that perform operations on a single operand, which means they work with only one value. These operators are commonly used to modify or evaluate the value of a single variable. There are several types of unary operators in Java:

* Unary Plus Operator (+):

The unary plus operator is used to indicate the positive value of a numeric expression. However, it doesn't really change the value of the operand.

```java
int num = +5; // num is assigned the value 5
```
  * Unary Minus Operator (-):

The unary minus operator is used to negate the value of a numeric expression. It changes a positive value to negative and vice versa.

```java
int num = -5; // num is assigned the value -5
```
* Increment Operator (++):

The increment operator increases the value of the operand by 1. It can be used in both prefix and postfix forms.

```java
int count = 10;
count++; // count is incremented to 11
```
* Decrement Operator (--):

The decrement operator decreases the value of the operand by 1. It can also be used in both prefix and postfix forms.

```java
int count = 10;
count--; // count is decremented to 9
```
* Logical Complement Operator (!):

The logical complement operator is used to invert the logical value of a boolean expression. If the expression is true, the operator makes it false and vice versa.

```java
boolean isTrue = true;
boolean isFalse = !isTrue; // isFalse is assigned the value false
```
* Bitwise Complement Operator (~):

The bitwise complement operator is used to invert the bits of a numeric expression. It changes 0s to 1s and 1s to 0s in the binary representation of the number.

```java
int num = 5; // Binary representation: 00000101
int complement = ~num; // Binary representation: 11111010
```

***5. Assignment Operators:***

Assignment operators are used to assign values to variables.

|Operator	|Example	|Same As|
|-|-|-|
|=	|x = 5|	x = 5|
|+=	|x += 3|	x = x + 3|
|-=	|x -= 3|	x = x - 3|
|*=	|x *= 3|	x = x * 3|
|/=	| /= 3|	x = x / 3|
|%=	|x %= 3|	x = x % 3|
|&=	|x &= 3|	x = x & 3|
|`|=`|x `|`= 3|	x = x `|` 3|
|^=	|x ^= 3	|x = x ^ 3|
|>>=|x >>= 3| x = x >> 3|
|<<=|x <<= 3	|x = x << 3|


***6. Bitwise Operators***

Bitwise operators are used to performing the manipulation of individual bits of a number. They can be used with any integral type (char, short, int, etc.). They are used when performing update and query operations of the Binary indexed trees. 

|Operators|Symbol|Uses|
|-|-|-|-|
|Bitwise AND|&|op1 & op2|
|Bitwise exclusive OR|^|op1 ^ op2|
|Bitwise inclusive OR|`|`|op1 `|` op2|
|Bitwise Compliment|~|~ op|
|Bitwise left shift|<<|op1 << op2|
|Bitwise right shift|>>|op1 >> op2|
|Unsigned Right Shift Operator|>>> op >>>|number of places to shift|

* **Bitwise AND (&)**

It is a binary operator denoted by the symbol &. It returns 1 if and only if both bits are 1, else returns 0. same as (true & false) = (false & false) = false and only (true & true ) is true, 
|x|y|x&y|
|-|-|-|
|0|0|0|
|0|1|0|
|1|1|1|

* **Bitwise OR (|)**

It is a binary operator denoted by the symbol | (pronounced as a pipe). It returns 1 if either of the bit is 1, else returns 0.

|x|y|x`|`y|
|-|-|-|
|0|0|0|
|0|1|1|
|1|1|1|

* **Bitwise XOR (^)**

It is a binary operator denoted by the symbol ^ (pronounced as caret). It returns 0 if both bits are the same, else returns 1.
|x|y|x^y|
|-|-|-|
|0|0|0|
|0|1|1|
|1|0|1|
|1|1|0|

* **Bitwise Complement (~)**

It is a unary operator denoted by the symbol ~ (pronounced as the tilde). It returns the inverse or complement of the bit. It makes every 0 a 1 and every 1 a 0.

|x|~x|
|-|-|
|1|0|
|0|1|

(~10) will be -11
bcz 00000000 00000000 00000000 00001010 complement of this will be
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 11111111 11111111 11111111 11110101 sign bit is -ve .

* **Bit-Shift Operators (Shift Operators)**
Shift operators are used to shift the bits of a number left or right, thereby multiplying or dividing the number by two, respectively. They can be used when we have to multiply or divide a number by two.
<br>
    * **Signed (or Bitwise) Right Shift Operator (>>)**
    if we write a>>n, it means to shift the bits of a number toward the right with a specified position (n). In the terms of mathematics, ***It also preserves the leftmost bit (sign bit). If 0 is presented at the leftmost bit, it means the number is positive. If 1 is presented at the leftmost bit, it means the number is negative.*** we can represent the signed right shift operator as follows:
      a >> n &#x2192; a/2<sup>n</sup>
<br>
       * The signed right shift operation shifts the bits of a number to the right by a specified number of positions.
       * For each position shifted, the number is effectively divided by 2.
       * For positive numbers, the behavior is similar to the left shift; the rightmost bits are shifted out, and the leftmost bits are filled with 0s.
       * *For negative numbers, the signed right shift preserves the sign bit (leftmost bit). It shifts the bits to the right, and the leftmost bits are filled with the original sign bit (1 in the case of negative numbers). This maintains the negative sign of the number after the shift.*
<br>
    * **Signed Left Shift Operator (<<)**
    The signed left shift operator (<<) shifts a bit pattern to the left. It is represented by the symbol <<. It also preserves the leftmost bit (sign bit). It does not preserve the sign bit.
       a << n &#x2192; a * (2<sup>n</sup>)
<br>
      * The left shift operation shifts the bits of a number to the left by a specified number of positions.
       * For each position shifted, the number is effectively multiplied by 2.
       * In binary, left shifting is equivalent to multiplying the number by 2^n, where n is the number of positions shifted.
       * *For both negative and positive numbers, left shifting fills the empty bits on the right with 0s.*
<br>
    * ***Unsigned Right Shift Operator (>>>)***
     It shifts a zero at the leftmost position and fills 0. It is denoted by the symbol >>>. Note that the leftmost position after >> depends on the sign bit. It does not preserve the sign bit.
        a >> n &#x2192; a/2<sup>n</sup>
    <br>
        * The unsigned right shift operation is similar to the signed right shift, but it treats the number as an unsigned value.
        * For positive numbers, the behavior is the same as the signed right shift; the rightmost bits are shifted out, and the leftmost bits are filled with 0s.
        * For negative numbers, the unsigned right shift treats the number as if it were a positive number, ignoring the sign bit. It shifts the bits to the right, and the leftmost bits are filled with 0s. This doesn't preserve the negative sign, and the result may not be as expected.

       ---

># Scope and Lifetime

***Instance Variables***
A variable which is declared inside a class and outside all the methods and blocks is an instance variable. The general scope of an instance variable is throughout the class except in static methods. The lifetime of an instance variable is until the object stays in memory.

***Class Variables***
A variable which is declared inside a class, outside all the blocks and is marked static is known as a class variable. The general scope of a class variable is throughout the class and the lifetime of a class variable is until the end of the program or as long as the class is loaded in memory.

***Local Variables***
All other variables which are not instance and class variables are treated as local variables including the parameters in a method. Scope of a local variable is within the block in which it is declared and the lifetime of a local variable is until the control leaves the block in which it is declared.

---

***Print Stars Pattern***
```java
//    *
//   **
//  ***
// ****
//*****

for(int i = 1;i < n;i++){
    for(int spaces = 1 ; spaces <= n-i ; spaces++){
        System.out.print(" ");
    }
    for(int stars = 1; stars <= i ; stars++){
        System.out.print("*");
    }
            System.out.println()
}
```

---

># break and continue
1. ***break statement:*** The break statement terminates the loop (for, while and do. while loop) immediately when it is encountered. As soon as break is encountered inside a loop, the loop terminates immediately. Hence the statement after loop will be executed next.
<br>
2. ***continue statement:*** The continue statement skips some statements inside the loop. The continue statement is used with decision making statement such as if...else. (caution always update the counter in case of while loop else loop will never end)

---
># Pass by value

***Call-by-reference or pass-by-reference is not supported in Java.*** Java supports ***pass-by-value*** only. In pass-by-value, any changes to a parameter inside the called method are not reflected outside the method's scope.

In ***pass-by-reference***, changes made to the parameters inside the method are also reflected outside. Though Java does not support pass-by-reference, we can achieve pass-by-reference in Java for non-primitives.

**Java Objects and Primitive Data Types:**

*In Java, we use two kinds of things to store information: objects and primitive data types.*

* *Objects are like complex boxes that can hold different pieces of information.*
* *Primitive data types are like simple boxes that hold just one piece of information, like a number or a letter.*

**Copying vs. Referencing:**

When we give something to a friend, we can either give them a copy or just tell them where to find it. Similarly, in Java:

* For objects (complex boxes), we tell Java where to find the box.
* For primitive data types (simple boxes), we make a copy of the box and give that to Java.
Passing Information to Methods:

Imagine you're giving a recipe to a friend. The recipe might need ingredients (information). In Java, methods are like recipes, and the information you give them is called arguments.

* **Parameters:** The things you mention in the recipe (method) are called parameters. They're like placeholders for ingredients.
* **Arguments:** The actual ingredients you use to make the dish (method) are called arguments. They're what you really need.

***How Java Handles It:***

* For objects (complex boxes), Java just tells the method where to find the box. So if you change something inside the box in the method, the original box outside the method also changes. So changes inside the box are seen by both the method and the original code.
<br>
* For primitive data types (simple boxes), Java makes a copy of the box and gives that to the method. So if you change something inside the copied box in the method, the original box outside the method doesn't change.


***Pass by Value Using Java Primitive Types***
```java
public class PassByValue {

  public static void main(String[] args) {
    int a = 2;
    int b = 3;
    add(a, b);
    System.out.println("Result from main: " + (a + b));
  }

  private static void add(int a, int b) {
    a = 10;
    System.out.println("Result from method: " + (a + b));
  }
}

Output
Result from method: 13
Result from main: 5
```

*Explanation:*

* When the variables a and b are passed as an argument to the add method, copies of these variables are created in the stack memory.
* These copied variables are passed to the add method.
* Hence, when a is changed inside the add method, it does affect the variable a defined in the main method.

***Pass by Value Using Java Objects***

```java
public class PassByValue {

  public static void main(String[] args) {
    Integer a = new Integer(2);
    Integer b = new Integer(3);
    add(a, b);
    System.out.println("Result from main: " + (a + b));
  }

  private static void add(Integer a, Integer b) {
    // If a is simply assigned a reference to a new object
    // in heap memory, the original argument in main method
    // does not change
    a = new Integer(10);
    System.out.println("Result from method: " + (a + b));
  }
}

Output
Result from method: 13
Result from main: 5
```

*Explanation:*

* In the above program, variables a and b in the main method store the references of both Integer objects created in the heap memory.
* Passing a and b as arguments to the add method creates copies of these variables/references in the stack memory.
* Point to note here is that these copied variables store the references to the same Integer objects created in the main method.
* Inside the add method, we are changing the object altogether. The a variable inside the add method is made to store the reference to a new Integer object created in the heap memory with the value 10.
* However, due to this operation, only the copied reference variable is affected and the original variable in the main method is not affected.
* Since there are no changes made to the Integer objects created in the main method, the sum inside the main method is 5 only.

***Pass by Value for non-primitives***
```java
class PassByValue {

  public static void main(String[] args) {
    Integer[] array = new Integer[2];
    array[0] = 2;
    array[1] = 3;
    add(array);
    System.out.println("Result from main: " + (array[0] + array[1]));
  }

  private static void add(Integer[] array) {
    array[0] = 10;
    System.out.println("Result from method: " + (array[0] + array[1]));
  }
}

Output
Result from method: 13
Result from main: 13
```


*Explanation:*

* The called method is able to modify the original object but not replace it with another object.
* In this example, when we create the array object in the main method, a new Integer array object is created in the heap memory. The array variable in the main method holds the reference to the same object.
* On passing array as an argument to the add method creates a copy of that reference in the stack memory. This copied reference/variable is passed to the add method.
* However, the point to note here is that the copied reference points to the same Integer array object that we created in the first step.
* Hence, when we modify the properties of the Integer array object inside the add method using the copied reference, these modifications are reflected in the heap memory.
* If we had reinitialized the array object with array = new Integer[2]; in the add() method, our result would have been different. Let’s see what the result would be.

***In Java, when you pass an object like an array to a method, you're actually passing the value of the reference to the object, not the entire object itself. This is where the term "pass by value" comes in, but it's important to note that the value being passed is the reference, not the object.
So, when you pass an array to a method, you're giving that method a copy of the reference to the same array in memory. This means that both the original code (the calling code) and the method have their own copies of the reference that point to the same array in memory. This is why modifications made to the array inside the method are reflected in the original array outside the method.
The confusion can arise because this behavior is similar to passing by reference in other programming languages. However, in Java, it's still technically "pass by value" because you're passing a copy of the reference's value.***

---
---

># Array
Java array is an object which contains elements of a similar data type. Additionally, The elements of an array are stored in a contiguous memory location. It is a data structure where we store similar elements. We can store only a fixed set of elements in a Java array.
Array in Java is index-based, the first element of the array is stored at the 0th index, 2nd element is stored on 1st index and so on.

When you create an array in Java, like,
```java
int arr[] = new int[3];
```
the array is essentially a block of memory allocated for holding three integers.
In memory, the variable arr will hold the memory address of the first element of the array. This address represents where the array data starts in memory.
So, when you access **arr[0]**, you're telling Java to go to the memory address stored in the variable arr (which points to the beginning of the array) and retrieve the value stored there.

This is how arrays work in many programming languages, allowing you to access elements using an index while the actual data is stored in memory sequentially.

***Contiguous Memory:***

When you create an array in Java, the elements of that array are stored in a sequence, one after another, in what's called contiguous memory. This means that the memory addresses of the elements are consecutive.

#### Primitive Data Type Arrays:

Let's take the example of an array of integers (int). An int in Java typically uses 4 bytes of memory. So, when you create an array of integers, each element takes up 4 bytes of memory.

If the array starts at memory address 1000, then:
1. Element at index 0 is at address 1000
2. Element at index 1 is at address 1004 (1000 + 4 bytes)
3. Element at index 2 is at address 1008 (1000 + 2 * 4 bytes)
4. And so on...

***example:***
Assuming we start at memory address 1000, here's how these binary numbers might be stored:
```java
int arr[] = {10,20,30};
```
**Memory Address 1000: 00000000 00000000 00000000 00001010 (Binary 10)
Memory Address 1004: 00000000 00000000 00000000 00010100 (Binary 20)
Memory Address 1008: 00000000 00000000 00000000 00011110 (Binary 30)**

Each address represents 4 bytes (32 bits), and the binary values are stored in little-endian format, where the least significant byte comes first.
So, the memory storage is indeed contiguous, with each value taking up 4 bytes, one after another. This allows for efficient access to the values using memory addresses.

#### Array of Objects:

For arrays of objects, it's a bit different because objects can vary in size. What's stored in the array are references (memory addresses) to those objects, not the objects themselves.

1. If you have an array of objects and it starts at memory address 2000, then:
2. The reference to the object at index 0 is at address 2000
3. The reference to the object at index 1 is at address 2004 (2000 + 4 bytes, assuming 4-byte memory addresses)
4. The reference to the object at index 2 is at address 2008 (2000 + 2 * 4 bytes)
5. And so on...

#### Accessing Elements:

*When you access an element in an array, Java uses the index to calculate the memory address where that element is stored. For primitive data types, like int, it directly knows the size of each element. For objects, it retrieves the reference from the array and then goes to the memory address where the actual object is stored.<br>
This contiguous storage in memory allows for efficient access to elements using their index, and it's one of the reasons arrays are so widely used in programming.*

**Remember that this explanation is a simplification for conceptual understanding. In real-world scenarios, memory management and addressing can involve more complexity due to factors like memory alignment, JVM optimizations, and more.**

---