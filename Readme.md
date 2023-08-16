[variables](#variables) | [Methods](#methods) | [Data Types in Java](#data-types-in-java) | [primitive](#there-are-8-types-of-primitive-data-types) | [Non-primitive](#non-primitive-data-types) | [Arithmetic Operators and there Precedence ](#arithmetic-operators-and-there-precedence-in-java) | [Decimal <==> Binary](#decimal-to-binary-and-binary-to-decimal) | [Chars](#how-char-is-going-to-store-in-memory) | [Typecasting](#typecasting) | [Some scanner options](#some-scanner-options)

># variables
A variable is the name of a reserved area allocated in memory. In other words, it is a name of the memory location. It is a combination of "vary + able" which means its value can be changed.
```java
int data=50;//Here data is variable
```
**Types of Variables**
There are three types of variables in Java:

* local variable
* instance variable
* static variable


1. ***Local Variable:***

Think of local variables as temporary notes you write on a sticky note while working on a task. These notes are specific to that task and are only relevant while you're working on it. Once you're done, you don't need those notes anymore.

In programming, local variables are like notes you create inside a method or a specific part of your code. They hold data that's needed temporarily for that part of the code. Once the method or code block is finished, the local variables disappear, just like your sticky notes after you're done with the task.

*Example:*
Imagine you're baking cookies. While you're mixing the ingredients, you might use a "mixing bowl" to keep track of the current mixture. That mixing bowl is like a local variable. It's relevant only while you're mixing the ingredients, and you don't need it once the cookies are baked.

*  A local variable is declared within a method or block of code.
* It is accessible only within the block where it's declared.
* Local variables must be initialized before they are used.
* They don't have default values like instance or class variables.

```java
void calculate() {
    int result = 10; // Local variable
    System.out.println(result);
}
```

2. ***Instance Variable (also called Fields):***

Imagine you have a personal notebook where you jot down important things about yourself. Each person has their own notebook, and what you write in your notebook is unique to you.

In programming, instance variables are like those personal notebooks. They belong to each individual object (instance) of a class. Each object can have its own set of instance variables, and the values in these variables can be different for each object.

*Example:*
Consider a class named Person. Each person has their own name and age, stored in instance variables. So, if you have a class instance for yourself and another for a friend, the name and age instance variables will hold different values for each of you.

* An instance variable is declared within a class but outside any method.
* Each instance (object) of the class has its own copy of the instance variable.
* Instance variables are created when an object is instantiated.
* They have default values (0, null, false) if not explicitly initialized.

```java
class Person {
    String name;    // Instance variable
    int age;        // Instance variable
}
```

3. ***Static Variable (also called Class Variable):***

Think of static variables as a shared whiteboard that everyone in a class can write on. Any updates you make on the whiteboard are visible to everyone who looks at it.

In programming, static variables are like shared information that's common to all instances of a class. These variables are shared among all objects of the class, and changes made to them are visible to all instances.

*Example:*
Imagine you're in a classroom, and there's a "class count" board that keeps track of the total number of students. Every time a student enters or leaves the class, the count changes. This "class count" board is like a static variable. All students see the same count, and any updates to it are shared among everyone.

* A static variable is declared using the static keyword within a class but outside any method.
* Unlike instance variables, static variables are shared among all instances of the class.
* They are created when the class is loaded into memory and exist for the entire program's lifetime.
* Static variables also have default values (0, null, false) if not explicitly initialized.
```java
class MathUtility {
    static final double PI = 3.14159; // Static variable
    static int counter = 0;          // Static variable
}
```

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

