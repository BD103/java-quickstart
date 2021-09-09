# Java Quickstart

_Written by [BD103](https://github.com/BD103)_

## Intro

Hello! Welcome to my wonderful tutorial on CS, coffee script!

...

Ok, not really. This is a guide to Java, and should give you enough skill to be able to understand other people's projects with the source code and Google. In this website we will be covering:

- Variables
- Methods
- Classes / Objects
- Scope
- Inheritence
- Interfaces
- Enums
- File handling
- A sample calculator program
- How to read Javadoc

Let's dig right in!

## Getting Java

Some computers already have Java installed. Open up Command Prompt and run the following:

```
$ java -version
```

If it's installed, you'll see something like this:

```
java version "11.0.1" 2018-10-16 LTS  
Java(TM) SE Runtime Environment 18.9 (build 11.0.1+13-LTS)  
Java HotSpot(TM) 64-Bit Server VM 18.9 (build 11.0.1+13-LTS, mixed mode)
```

If you don't have it installed, you can get it at [oracle.com](https://www.oracle.com/technetwork/java/javase/overview/index.html). This tutorial is for Java 16, but you should be able to do most of it in any version. (Recommended minimun version is 8!)

If you can't install it, or are using a Chromebook, check out [replit.com](https://replit.com). It is a free online IDE that I use for programming projects. It supports Java 11, and is probably your best option if you're new.

If you want the real deal IDE, check out [Jetbrain's IntelliJ IDEA](https://www.jetbrains.com/idea/). There are both free and paid versions that don't have much of a difference. This is a *must have* if you want to do more than playing around.

## Getting started

Now you have Java! (Hopefully. [If not, submit an issue on the repo.](https://github.com/BD103/java-quickstart/issues) I will gladly help you!) Let's get started by creating our first program.

```java
// Main.java
public class Main {
	public static void main(String[] args) {
		System.out.println("Hello, world!");
	}
}
```

Don't worry about not understanding the code above. Just focus on running the program!

### Command Line

```
$ javac Main.java
$ java Main
```

### Replit

Click the run button

### IntelliJ IDEA

Find the green triangle next to the `public class Main`. Click it and click `Main.main()`.

---

Let's break down the program.

```java
/* All files need to have this statement
*  Replace "Main" with the name of the file
*  File names should begin with a capital letter
*  Main.java, MyClass.java, Something1.java, etc. */
public class Main {
	/* Methods phrased like the following
	*  Can be run from the command line
	*  If it doesn't have this statement then it can't be run */
	public static void main(String[] args) {
		// Insert code to be run here
		// This prints text to the console
		System.out.println("Hello, world");
	}
}
```

> **Cool fact:** Writing a `//` means that any following text will not be run
> This is called a comment.
> Writing `/*` means that no text will be run until a `*/` is typed

## Variables

You've learned how to print things to the console. What about storing data? Java is an object-oriented statically-typed language. Let's break this down

- Typed - This means that data is stored using **types**. Types can be anything from text to numbers to binary.
- Static - This means that once you set the type of data, you cannot change it
- Object-oriented - This means that you can create your own complex type *blueprints*, then create data from 

Let's get on with some examples:

```java
public class Main {
    public static void main(String[] args) {
        int x = 1;
        System.out.println(x);
    }
}
```

There, we created a variable called `x`. Its value is 1. Any time you write `x`, it will be substituted for 1. Some variable types include:

```java
String text = "this is some text!";
int integer = 1; // positive or negative non-decimal number
float floatingNumber = 5.89; // positive or negative decimal number
char character = 'e'; // single letter
boolean yesOrNo = true; // true or false
```

> Variables are created using the pattern `type name = value;`

These are some cool examples, but what if I want to overwrite a variable?

```java
int number = 1;
number = 2;
System.out.println(number);
// 2
```

You can also create a variable without giving it value!

```java
String name;
name = "Bob";
System.out.println(name);
// Bob
```

But what if you don't want anyone to change you value? Use the `final` keyword.

```java
final float x = 1.5;
x = 2.0; // This will raise an error! You cannot change a final variable once created.
```

### Math

Let's do some operations with numbers!

```java
int x = 100 + 25; // 125
int y = x + 75; // 200
int z = x + y; // 325
```

You can use many arithmetic operators, not just the plus sign.

|Operator|Name|Description|Example|
|-|-|-|-|
|+|Addition|Adds together two values|x + y|
|-|Subtraction|Subtracts one value from another|x - y|
|*|Multiplication|Multiplies two values|x * y|
|/|Division|Divides one value from another|x / y|
|%|Modulus|Returns the division remainder|x % y|
|++|Increment|Increases a value by 1|x++|
|--|Decrement|Decreases a value by 1|x--|

You can also use assignment operators:

```java
int x = 8;
x += 2; // 10
```

|Operator|Example|Same As|
|-|-|-|
|=|x = 5|N/A|
|+=|x += 5|x = x + 5|
|-=|x -= 5|x = x - 5|
|*=|x *= 5|x = x * 5|
|/=|x /= 5|x = x / 5|
|%=|x %= 5|x = x % 5|
|&=|x &= 5|x = x & 5|
|\|=|x \|= 5|x = x \| 5|
|^=|x ^= 5|x = x ^ 5|
|>>=|x >>= 5|x = x >> 5|
|<<=|x <<= 5|x = x << 5|

## If / Else Statement

What if you wanted to detect if something is true?
For instance, what if you wanted to print "yay!" if x is greater than 5, but print "eh" if not?
I present to you: **if / else statements**!

```java
int x = 6;
if (x > 5) {
    System.out.println("yay!");
} else {
    System.out.println("eh");
}
```

If statements follow the general pattern:

```java
if (condition) {
    code
}
```

> The else statement should be appended after and if statement if you want to detect whether something worked or not
> You can also chain them!

```java
if (condition) {
    
} else if (condition) {
    
} else {
    
}
```

|Condition|Name|Example|
|-|-|-|
|true|True|true (always runs)|
|false|False|false (never runs)|
|==|Equal to|x == y|
|!=|Not equal to|x != y|
|>|Greater than|x > y|
|<|Less than|x < y|
|>=|Greater than or equal to|x >= y|
|<==|Less than or equal to|x <== y|
|&&|And|x == y && w == z|
|\|\||Or|x == y \|\| w == z|
|!|Not|!(x == y && w == z)|
