# Constructors in Java

Constructor is a block of code that initializes the newly created object.

Constructor has same name as the class and looks like this in a java code.

```java
public class MyClass{
   //This is the constructor
   MyClass(){
   }
   ..
}
```

## How does a constructor work

```java
MyClass obj = new MyClass();
```

The new keyword here creates the object of class MyClass and invokes the constructor to initialize this newly created object

#A simple constructor program in java

Here we have created an object obj of class Hello and then we displayed the instance variable name of the object. 
As you can see that the output is BeginnersBook.com which is what we have passed to the name during initialization in constructor. 
This shows that when we created the object obj the constructor got invoked. In this example we have used this keyword, 
which refers to the current object, object obj in this example. We will cover this keyword in detail in the next tutorial.

```java
public class Hello {
   String name;
   //Constructor
   Hello(){
      this.name = "BeginnersBook.com";
   }
   public static void main(String[] args) {
      Hello obj = new Hello();
      System.out.println(obj.name);
   }
}
```

### Output:

BeginnersBook.com


Constructors in Java – A complete study!!

BY CHAITANYA SINGH | FILED UNDER: OOPS CONCEPT


 
Constructor is a block of code that initializes the newly created object. A constructor resembles an instance method in java but it’s not a method as it doesn’t have a return type. In short constructor and method are different(More on this at the end of this guide). People often refer constructor as special type of method in Java.

Constructor has same name as the class and looks like this in a java code.

public class MyClass{
   //This is the constructor
   MyClass(){
   }
   ..
}
Note that the constructor name matches with the class name and it doesn’t have a return type.

How does a constructor work

To understand the working of constructor, lets take an example. lets say we have a class MyClass.
When we create the object of MyClass like this:


 
MyClass obj = new MyClass()
The new keyword here creates the object of class MyClass and invokes the constructor to initialize this newly created object.

You may get a little lost here as I have not shown you any initialization example, lets have a look at the code below:

A simple constructor program in java

Here we have created an object obj of class Hello and then we displayed the instance variable name of the object. As you can see that the output is BeginnersBook.com which is what we have passed to the name during initialization in constructor. This shows that when we created the object obj the constructor got invoked. In this example we have used this keyword, which refers to the current object, object obj in this example. We will cover this keyword in detail in the next tutorial.

public class Hello {
   String name;
   //Constructor
   Hello(){
      this.name = "BeginnersBook.com";
   }
   public static void main(String[] args) {
      Hello obj = new Hello();
      System.out.println(obj.name);
   }
}
Output:

BeginnersBook.com
new keyword invoked the constructor

## Types of Constructors

There are three types of constructors: Default, No-arg constructor and Parameterized.
![alt text](https://beginnersbook.com/wp-content/uploads/2013/03/types_of_constructor.jpg)

### Default constructor
![alt text](https://beginnersbook.com/wp-content/uploads/2013/03/default_constructor.jpg)


### no-arg constructor:

Constructor with no arguments is known as no-arg constructor. The signature is same as default constructor, 
however body can have any code unlike default constructor where the body of the constructor is empty.

### Parameterized constructor

Constructor with arguments(or you can say parameters) is known as Parameterized constructor.

### What if you implement only parameterized constructor in class

```java
class Example3
{
      private int var;
      public Example3(int num)
      {
             var=num;
      }
      public int getValue()
      {
              return var;
      }
      public static void main(String args[])
      {
              Example3 myobj = new Example3();
              System.out.println("value of var is: "+myobj.getValue());
      }
}
```
Output: It will throw a compilation error. The reason is, the statement Example3 myobj = new Example3() is invoking a default constructor which we don’t have in our program. when you don’t implement any constructor in your class, compiler inserts the default constructor into your code, however when you implement any constructor (in above example I have implemented parameterized constructor with int parameter), 
then you don’t receive the default constructor by compiler into your code.

### Super()

Whenever a child class constructor gets invoked it implicitly invokes the constructor of parent class. You can also say that the compiler inserts a super(); 
statement at the beginning of child class constructor.

## Quick Recap

1. Every class has a constructor whether it’s a normal class or a abstract class.
2. Constructors are not methods and they don’t have any return type.
3. Constructor name should match with class name .
4. Constructor can use any access specifier, they can be declared as private also. Private constructors are possible in java but there scope is within the class only.
5. Like constructors method can also have name same as class name, but still they have return type, though which we can identify them that they are methods not constructors.
6. If you don’t implement any constructor within the class, compiler will do it for.
7. this() and super() should be the first statement in the constructor code. If you don’t mention them, compiler does it for you accordingly.
8. Constructor overloading is possible but overriding is not possible. Which means we can have overloaded constructor in our class but we can’t override a constructor.
9. Constructors can not be inherited.
10. If Super class doesn’t have a no-arg(default) constructor then compiler would not insert a default constructor in child class as it does in normal scenario.
11. Interfaces do not have constructors.
12. Abstract class can have constructor and it gets invoked when a class, which implements interface, is instantiated. (i.e. object creation of concrete class).
13. A constructor can also invoke another constructor of the same class – By using this(). If you want to invoke a parameterized constructor then do it like this: this(parameter list).

## Difference between Constructor and Method

1. The purpose of constructor is to initialize the object of a class while the purpose of a method is to perform a task by executing java code.
2. Constructors cannot be abstract, final, static and synchronised while methods can be.
3. Constructors do not have return types while methods do.

## Java – Constructor in Interface?

This is a most frequently asked java interview question. The answer is No, interface cannot have constructors. In this post we will discuss why constructors are not allowed in interface?

All the methods of interface doesn’t have body so there is no need to call the methods in the interface itself. In order to call any method we need an object since there is no need to have object of interface, there is no need of having constructor in interface (Constructor is being called during creation of object).

Reference: https://beginnersbook.com/2013/03/constructors-in-java/
