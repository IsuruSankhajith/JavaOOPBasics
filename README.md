# Java OOP Concepts

This repository is designed to help beginners understand Object-Oriented Programming (OOP) concepts in Java. It covers key principles of OOP, demonstrates them with code examples, and explains their practical applications.

## Table of Contents

1. [Introduction to OOP](#introduction-to-oop)
2. [Classes and Objects](#classes-and-objects)
3. [Encapsulation](#encapsulation)
4. [Inheritance](#inheritance)
5. [Polymorphism](#polymorphism)
6. [Abstraction](#abstraction)
7. [Key OOP Concepts in Java](#key-oop-concepts-in-java)
8. [Design Principles and Patterns](#design-principles-and-patterns)
9. [Practical Applications](#practical-applications)

### 1.Introduction to OOP

#### **Definition of OOP**
Object-Oriented Programming (OOP) is a programming paradigm centered around the concept of objects. Objects are instances of classes, which are blueprints for creating entities that encapsulate data (attributes) and behaviors (methods). OOP allows for the modeling of real-world entities in a structured and organized way.

#### **Four Pillars of OOP**
1. **Encapsulation**: 
   - **Definition**: Encapsulation is the process of bundling data (attributes) and methods (functions) that operate on the data into a single unit, or class. It also restricts direct access to some of the object's components, which is a way of preventing accidental interference and misuse of the methods and data.
   - **Example**: Using private variables with public getter and setter methods.

2. **Inheritance**:
   - **Definition**: Inheritance is a mechanism where one class (child or subclass) acquires the properties and behaviors of another class (parent or superclass). It allows for code reuse and the creation of a hierarchical relationship between classes.
   - **Example**: A `Car` class inheriting from a `Vehicle` class.

3. **Polymorphism**:
   - **Definition**: Polymorphism allows objects of different classes to be treated as objects of a common super class. It typically occurs when a parent class reference is used to refer to a child class object.
   - **Example**: Method overriding where a subclass provides a specific implementation of a method already defined in its superclass.

4. **Abstraction**:
   - **Definition**: Abstraction involves hiding the complex implementation details of an object and exposing only the essential features to the user. It focuses on what an object does rather than how it does it.
   - **Example**: Using interfaces and abstract classes to define methods that must be implemented by derived classes.

#### **Benefits of OOP**
- **Modularity**: OOP allows developers to break down complex software into smaller, more manageable modules (classes). Each class can be developed, tested, and maintained independently.
- **Code Reusability**: Through inheritance, classes can be reused across different parts of a program or in different projects, reducing the need for redundant code.
- **Scalability and Maintainability**: OOP makes it easier to manage and scale large codebases by promoting a clean and organized structure.
- **Flexibility through Polymorphism**: Polymorphism allows for flexibility in code, enabling developers to introduce new classes with minimal changes to existing code.
- **Security**: Encapsulation helps protect an object’s state by controlling access to its data and methods, reducing the chances of unintended interference or misuse.

Here's a more detailed breakdown of the **"Classes and Objects"** section for your notes on OOP in Java:

### Classes and Objects

#### **Class Definition**
- A class is a blueprint or template for creating objects. It defines the properties (fields) and behaviors (methods) that the objects created from the class can have.
- Syntax:
  ```java
  class ClassName {
      // Fields (attributes or variables)
      // Methods (functions or procedures)
  }
  ```

#### **Creating Objects**
- Objects are instances of a class. When you create an object, you're creating an instance of the class with specific values for its fields.
- Syntax:
  ```java
  ClassName objectName = new ClassName();
  ```
- Example:
  ```java
  class Dog {
      String name;
      int age;
  }
  
  public class Main {
      public static void main(String[] args) {
          Dog myDog = new Dog(); // Creating an object of the Dog class
          myDog.name = "Buddy";
          myDog.age = 3;
      }
  }
  ```

#### **Constructors**
- A constructor is a special method used to initialize objects. It is called when an object of a class is created.
- **Default Constructor**: If no constructor is defined, Java provides a default constructor.
- **Parameterized Constructor**: A constructor that accepts parameters to set the initial state of an object.
- Syntax:
  ```java
  class ClassName {
      // Constructor
      ClassName() {
          // Initialization code
      }
      
      // Parameterized Constructor
      ClassName(String param) {
          // Initialization code
      }
  }
  ```
- Example:
  ```java
  class Dog {
      String name;
      int age;
      
      // Constructor
      Dog(String name, int age) {
          this.name = name;
          this.age = age;
      }
  }
  
  public class Main {
      public static void main(String[] args) {
          Dog myDog = new Dog("Buddy", 3); // Using parameterized constructor
      }
  }
  ```

#### **Member Variables (Fields)**
- Member variables or fields are the properties or attributes of a class. They define the state of an object.
- Fields can be of any data type, including objects of other classes.
- Example:
  ```java
  class Dog {
      String name; // Field
      int age;     // Field
  }
  ```

#### **Methods**
- Methods define the behaviors of a class. They can perform actions and return values.
- Syntax:
  ```java
  class ClassName {
      void methodName() {
          // Method code
      }
      
      int anotherMethod() {
          return someValue;
      }
  }
  ```
- Example:
  ```java
  class Dog {
      String name;
      int age;
      
      void bark() {
          System.out.println(name + " says: Woof!");
      }
  }
  
  public class Main {
      public static void main(String[] args) {
          Dog myDog = new Dog("Buddy", 3);
          myDog.bark(); // Calling the method
      }
  }
  ```

#### **`this` Keyword**
- The `this` keyword refers to the current instance of the class. It is used to differentiate between instance variables and parameters with the same name.
- Example:
  ```java
  class Dog {
      String name;
      int age;
      
      Dog(String name, int age) {
          this.name = name; // 'this.name' refers to the instance variable, 'name' refers to the parameter
          this.age = age;
      }
  }
  ```

#### **Example: Basic Class and Object Creation**
- Bringing it all together:
  ```java
  class Dog {
      String name;
      int age;
      
      // Constructor
      Dog(String name, int age) {
          this.name = name;
          this.age = age;
      }
      
      // Method
      void bark() {
          System.out.println(name + " says: Woof!");
      }
  }
  
  public class Main {
      public static void main(String[] args) {
          // Creating an object of the Dog class
          Dog myDog = new Dog("Buddy", 3);
          
          // Accessing fields and methods
          System.out.println("My dog's name is " + myDog.name);
          myDog.bark();
      }
  }
  ```
- **Explanation**: This example shows how to define a class (`Dog`), create an object of that class (`myDog`), initialize it using a constructor, and call its method (`bark`).

Here’s a detailed breakdown of the notes on **Encapsulation** in Java:

### Encapsulation

#### **Definition**
Encapsulation is one of the four fundamental OOP concepts in Java. It refers to the bundling of data (variables) and methods (functions) that operate on the data into a single unit or class. Encapsulation helps to protect the data from outside interference and misuse by restricting access to certain components. This is often achieved through access modifiers and the use of getter and setter methods.

#### **Access Modifiers**
Access modifiers control the visibility of class members (fields, methods, constructors) from other classes. Java provides four access levels:

- **`private`**: The member is accessible only within the same class.
- **`protected`**: The member is accessible within the same package and by subclasses.
- **`public`**: The member is accessible from any other class.
- **`default` (no modifier)**: The member is accessible only within the same package.

| Modifier  | Class | Package | Subclass | World |
|-----------|-------|---------|----------|-------|
| `private` | Yes   | No      | No       | No    |
| `default` | Yes   | Yes     | No       | No    |
| `protected` | Yes | Yes     | Yes      | No    |
| `public`  | Yes   | Yes     | Yes      | Yes   |

#### **Getters and Setters**
Getters and setters are methods used to access and update the value of private variables. They provide a controlled way to access and modify the data, ensuring that any validation or logic required is handled appropriately.

- **Getter**: A method that returns the value of a private variable.
  ```java
  public class Person {
      private String name;
      
      public String getName() {
          return name;
      }
  }
  ```
- **Setter**: A method that sets the value of a private variable.
  ```java
  public class Person {
      private String name;
      
      public void setName(String name) {
          this.name = name;
      }
  }
  ```

#### **Example: Encapsulation in Practice**
Here’s a simple example to demonstrate encapsulation in Java:

```java
public class BankAccount {
    // Private fields to protect the data
    private String accountNumber;
    private double balance;

    // Constructor
    public BankAccount(String accountNumber, double initialBalance) {
        this.accountNumber = accountNumber;
        this.balance = initialBalance;
    }

    // Getter for accountNumber
    public String getAccountNumber() {
        return accountNumber;
    }

    // Getter for balance
    public double getBalance() {
        return balance;
    }

    // Setter for balance (with some validation)
    public void deposit(double amount) {
        if (amount > 0) {
            balance += amount;
        }
    }

    // Method to withdraw money (with validation)
    public void withdraw(double amount) {
        if (amount > 0 && amount <= balance) {
            balance -= amount;
        }
    }
}
```

In this example, the `BankAccount` class encapsulates the account number and balance. The balance can only be modified through the `deposit` and `withdraw` methods, ensuring that the balance is always valid. This encapsulation helps maintain the integrity of the data and prevents unauthorized or unintended changes.

### Inheritance

**Definition:**
Inheritance is one of the core concepts of Object-Oriented Programming (OOP) that allows a new class (called a subclass or derived class) to inherit the properties and behavior (fields and methods) of an existing class (called a superclass or base class). This promotes code reusability and establishes a relationship between classes.

**Types of Inheritance:**
1. **Single Inheritance:**
   - In single inheritance, a class inherits from only one superclass.
   - **Example:**
     ```java
     class Animal {
         void eat() {
             System.out.println("Eating...");
         }
     }

     class Dog extends Animal {
         void bark() {
             System.out.println("Barking...");
         }
     }
     ```
   - In this example, `Dog` inherits the `eat()` method from `Animal`.

2. **Multilevel Inheritance:**
   - In multilevel inheritance, a class is derived from a class that is also derived from another class.
   - **Example:**
     ```java
     class Animal {
         void eat() {
             System.out.println("Eating...");
         }
     }

     class Dog extends Animal {
         void bark() {
             System.out.println("Barking...");
         }
     }

     class Puppy extends Dog {
         void weep() {
             System.out.println("Weeping...");
         }
     }
     ```
   - In this example, `Puppy` inherits `bark()` from `Dog` and `eat()` from `Animal`.

3. **Hierarchical Inheritance:**
   - In hierarchical inheritance, multiple classes inherit from a single superclass.
   - **Example:**
     ```java
     class Animal {
         void eat() {
             System.out.println("Eating...");
         }
     }

     class Dog extends Animal {
         void bark() {
             System.out.println("Barking...");
         }
     }

     class Cat extends Animal {
         void meow() {
             System.out.println("Meowing...");
         }
     }
     ```
   - In this example, both `Dog` and `Cat` inherit the `eat()` method from `Animal`.

**`super` Keyword:**
- The `super` keyword in Java is used to refer to the immediate parent class object.
- It can be used to:
  - **Call the superclass constructor**: This is useful when the subclass needs to invoke the parent class constructor explicitly.
  - **Access superclass methods**: When a subclass method overrides a superclass method, `super.methodName()` can be used to call the superclass method.
- **Example:**
  ```java
  class Animal {
      Animal() {
          System.out.println("Animal is created");
      }
  }

  class Dog extends Animal {
      Dog() {
          super(); // calls the constructor of Animal
          System.out.println("Dog is created");
      }
  }
  ```

**Method Overriding:**
- Method overriding occurs when a subclass provides a specific implementation of a method that is already defined in its superclass.
- The method in the subclass must have the same name, return type, and parameters as the method in the superclass.
- **Example:**
  ```java
  class Animal {
      void sound() {
          System.out.println("Animal makes a sound");
      }
  }

  class Dog extends Animal {
      @Override
      void sound() {
          System.out.println("Dog barks");
      }
  }
  ```
- Here, the `sound()` method in `Dog` overrides the `sound()` method in `Animal`.

**`final` Keyword:**
- The `final` keyword in Java is used to:
  - **Prevent inheritance**: A class declared as `final` cannot be subclassed.
  - **Prevent method overriding**: A method declared as `final` cannot be overridden by subclasses.
- **Example:**
  ```java
  final class Animal {
      void eat() {
          System.out.println("Eating...");
      }
  }

  // class Dog extends Animal { // This will cause a compilation error
  // }

  class Bird {
      final void fly() {
          System.out.println("Flying...");
      }
  }

  class Sparrow extends Bird {
      // void fly() { // This will cause a compilation error
      //    System.out.println("Sparrow is flying...");
      // }
  }
  ```

**Example: Implementing Inheritance in Java:**
```java
class Animal {
    void eat() {
        System.out.println("Animal is eating");
    }
}

class Dog extends Animal {
    void bark() {
        System.out.println("Dog is barking");
    }

    @Override
    void eat() {
        super.eat(); // calls the superclass's eat method
        System.out.println("Dog is eating");
    }
}

public class Main {
    public static void main(String[] args) {
        Dog d = new Dog();
        d.eat();  // Calls the overridden eat method
        d.bark(); // Calls the bark method from Dog
    }
}
```
- **Explanation:**
  - The `Dog` class inherits from `Animal`.
  - The `Dog` class overrides the `eat()` method and also calls the `eat()` method of its superclass using `super.eat()`.
  - The `Main` class demonstrates creating a `Dog` object and calling its methods.

  ### Polymorphism

#### **Definition**
Polymorphism is one of the core concepts of Object-Oriented Programming (OOP). It refers to the ability of a single function, method, or object to behave in different ways based on the context. In Java, polymorphism allows objects to be treated as instances of their parent class rather than their actual class. This enables a single interface to represent different underlying forms (data types).

#### **Compile-time Polymorphism (Method Overloading)**
Compile-time polymorphism, also known as method overloading, occurs when multiple methods in the same class share the same name but have different parameters (different number, type, or order of parameters). The method to be called is determined at compile time based on the method signature.

**Key Points:**
- **Same Method Name, Different Parameters**: Multiple methods can have the same name as long as their parameters differ.
- **Resolved at Compile Time**: The compiler determines which method to call based on the method signature.
- **Example**:
   ```java
   class Calculator {
       // Method with two int parameters
       int add(int a, int b) {
           return a + b;
       }

       // Method with three int parameters
       int add(int a, int b, int c) {
           return a + b + c;
       }

       // Method with two double parameters
       double add(double a, double b) {
           return a + b;
       }
   }

   public class Main {
       public static void main(String[] args) {
           Calculator calc = new Calculator();
           System.out.println(calc.add(5, 10));       // Calls add(int, int)
           System.out.println(calc.add(5, 10, 15));   // Calls add(int, int, int)
           System.out.println(calc.add(5.5, 10.5));   // Calls add(double, double)
       }
   }
   ```

#### **Runtime Polymorphism (Method Overriding)**
Runtime polymorphism, also known as method overriding, occurs when a subclass provides a specific implementation of a method that is already defined in its superclass. The method that gets called is determined at runtime based on the actual object's class.

**Key Points:**
- **Method in Subclass Overrides Method in Superclass**: The subclass method must have the same name, return type, and parameters as the method in the superclass.
- **Resolved at Runtime**: The JVM determines which method to call based on the object type at runtime.
- **Example**:
   ```java
   class Animal {
       void sound() {
           System.out.println("Animal makes a sound");
       }
   }

   class Dog extends Animal {
       @Override
       void sound() {
           System.out.println("Dog barks");
       }
   }

   class Cat extends Animal {
       @Override
       void sound() {
           System.out.println("Cat meows");
       }
   }

   public class Main {
       public static void main(String[] args) {
           Animal myAnimal = new Animal();  // Animal reference, Animal object
           Animal myDog = new Dog();        // Animal reference, Dog object
           Animal myCat = new Cat();        // Animal reference, Cat object

           myAnimal.sound();  // Outputs: Animal makes a sound
           myDog.sound();     // Outputs: Dog barks
           myCat.sound();     // Outputs: Cat meows
       }
   }
   ```

#### **Upcasting and Downcasting**
**Upcasting** is the process of treating an object of a subclass as an object of its superclass. It is always safe and done implicitly. **Downcasting** is the reverse process, where a reference of a superclass is cast to a subclass. Downcasting is not always safe and requires explicit casting.

**Key Points:**
- **Upcasting**: Automatically performed by the compiler, e.g., `Animal myDog = new Dog();`
- **Downcasting**: Must be done explicitly, e.g., `Dog myRealDog = (Dog) myAnimal;`
- **Example**:
   ```java
   class Animal {
       void sound() {
           System.out.println("Animal makes a sound");
       }
   }

   class Dog extends Animal {
       void sound() {
           System.out.println("Dog barks");
       }

       void wagTail() {
           System.out.println("Dog wags its tail");
       }
   }

   public class Main {
       public static void main(String[] args) {
           Animal myAnimal = new Dog(); // Upcasting
           myAnimal.sound(); // Outputs: Dog barks

           // Downcasting
           if (myAnimal instanceof Dog) {
               Dog myDog = (Dog) myAnimal;
               myDog.wagTail(); // Outputs: Dog wags its tail
           }
       }
   }
   ```

#### **Example: Polymorphism in Action**
Here’s a practical example to demonstrate polymorphism:

```java
abstract class Shape {
    abstract void draw();
}

class Circle extends Shape {
    @Override
    void draw() {
        System.out.println("Drawing a Circle");
    }
}

class Rectangle extends Shape {
    @Override
    void draw() {
        System.out.println("Drawing a Rectangle");
    }
}

class Triangle extends Shape {
    @Override
    void draw() {
        System.out.println("Drawing a Triangle");
    }
}

public class Main {
    public static void main(String[] args) {
        Shape shape1 = new Circle();
        Shape shape2 = new Rectangle();
        Shape shape3 = new Triangle();

        shape1.draw(); // Outputs: Drawing a Circle
        shape2.draw(); // Outputs: Drawing a Rectangle
        shape3.draw(); // Outputs: Drawing a Triangle
    }
}
```

In this example, the `draw()` method is called on different objects of type `Shape`, but each object behaves according to its actual class (either `Circle`, `Rectangle`, or `Triangle`). This demonstrates runtime polymorphism in action.

### Abstraction

#### **Definition**
Abstraction is one of the fundamental principles of OOP. It involves hiding the complex implementation details and showing only the essential features of an object. In other words, abstraction allows you to focus on what an object does rather than how it does it.

#### **Abstract Classes**
- An abstract class in Java is a class that cannot be instantiated directly. It can have abstract methods (methods without a body) and concrete methods (methods with an implementation).
- Abstract classes are used when you have a base class that should not be instantiated but instead, should provide common functionality to its subclasses.
- **Key Points**:
  - Declared using the `abstract` keyword.
  - Can have both abstract and non-abstract methods.
  - Can contain constructors and member variables.
  - Subclasses must either implement all abstract methods or be declared abstract themselves.

```java
abstract class Animal {
    // Abstract method (no body)
    abstract void makeSound();

    // Concrete method
    void sleep() {
        System.out.println("Sleeping...");
    }
}

class Dog extends Animal {
    // Implementing the abstract method
    void makeSound() {
        System.out.println("Bark");
    }
}
```

#### **Interfaces**
- An interface in Java is a reference type, similar to a class, that can contain only abstract methods (until Java 8) and constants. Since Java 8, interfaces can also have default methods (methods with a body) and static methods.
- Interfaces are used to specify what a class must do, but not how it should do it. A class can implement multiple interfaces, which allows for multiple inheritance.
- **Key Points**:
  - Declared using the `interface` keyword.
  - All methods in an interface are implicitly `public` and `abstract` (except for default and static methods).
  - Interfaces cannot have constructors.
  - A class that implements an interface must provide implementations for all its methods.

```java
interface Animal {
    void makeSound(); // Abstract method
}

class Dog implements Animal {
    public void makeSound() {
        System.out.println("Bark");
    }
}
```

#### **Difference between Abstract Classes and Interfaces**
- **Multiple Inheritance**: A class can implement multiple interfaces but can only extend one abstract class.
- **Method Implementation**: Abstract classes can have both abstract and concrete methods, while interfaces primarily have abstract methods (with default and static methods as exceptions).
- **Constructor**: Abstract classes can have constructors, while interfaces cannot.
- **Usage**: Use abstract classes when there is a clear hierarchy or shared code across classes. Use interfaces when you need to define a contract for what a class should do without dictating how it should do it.

| **Feature**                     | **Abstract Class**                | **Interface**                     |
|---------------------------------|-----------------------------------|-----------------------------------|
| Inheritance                     | Single inheritance                | Multiple inheritance              |
| Method Implementation           | Can have both abstract and concrete methods | Only abstract methods (default/static methods since Java 8) |
| Constructors                    | Can have constructors             | Cannot have constructors          |
| Access Modifiers                | Can have all types of access modifiers | Methods are `public` by default  |
| Use Case                        | Shared base functionality, strong hierarchy | Loose coupling, multiple behaviors  |

#### **Example: Implementing Abstraction**

```java
abstract class Shape {
    abstract void draw(); // Abstract method
}

class Circle extends Shape {
    void draw() {
        System.out.println("Drawing a Circle");
    }
}

class Rectangle extends Shape {
    void draw() {
        System.out.println("Drawing a Rectangle");
    }
}

interface Drawable {
    void draw();
}

class Triangle implements Drawable {
    public void draw() {
        System.out.println("Drawing a Triangle");
    }
}

public class Main {
    public static void main(String[] args) {
        Shape circle = new Circle();
        Shape rectangle = new Rectangle();
        circle.draw();
        rectangle.draw();

        Drawable triangle = new Triangle();
        triangle.draw();
    }
}
```

**Explanation**: 
- The `Shape` class is an abstract class with an abstract method `draw()`. `Circle` and `Rectangle` extend `Shape` and provide specific implementations of `draw()`.
- The `Drawable` interface defines a `draw()` method. The `Triangle` class implements this interface, providing its own implementation of `draw()`.
- This example shows how abstraction allows different shapes to be drawn, whether through abstract classes or interfaces, focusing on "what" is being drawn rather than "how" it is drawn.

Here's a more detailed breakdown for the section on **Key OOP Concepts in Java**:

### 7. **Key OOP Concepts in Java**

#### 7.1 **Static vs. Instance Members**
   - **Static Members:**
     - Belong to the class, not instances.
     - Can be accessed without creating an object.
     - `static` keyword used for fields and methods.
     - Common use cases: Utility methods, constants.
     - Example:
       ```java
       public class MyClass {
           static int staticVar = 10;
           int instanceVar = 20;

           static void staticMethod() {
               System.out.println("Static method called");
           }
       }
       ```
   - **Instance Members:**
     - Belong to instances of the class.
     - Each object has its own copy.
     - Accessed through object references.
     - Example:
       ```java
       MyClass obj = new MyClass();
       obj.instanceVar = 30;
       ```

#### 7.2 **Inner Classes**
   - **Types of Inner Classes:**
     - **Member Inner Class:** Defined within another class.
     - **Static Nested Class:** Inner class with the `static` modifier.
     - **Local Inner Class:** Defined within a method.
     - **Anonymous Inner Class:** Class without a name, often used for implementing interfaces or abstract classes on the fly.
   - **Purpose of Inner Classes:**
     - Encapsulation: Hide implementation details.
     - Logical grouping: Relate closely to the outer class.
   - **Example:**
     ```java
     public class OuterClass {
         class InnerClass {
             void display() {
                 System.out.println("Inner class method");
             }
         }
     }
     ```

#### 7.3 **Packages**
   - **Definition:**
     - A namespace for organizing classes and interfaces.
     - Helps avoid naming conflicts.
   - **Creating Packages:**
     - Use `package` keyword.
     - Example:
       ```java
       package com.example.myapp;
       public class MyClass {
           // Class code
       }
       ```
   - **Importing Packages:**
     - Use `import` keyword.
     - Example:
       ```java
       import java.util.List;
       ```
   - **Access Control:**
     - Classes in the same package can access each other’s package-private members.

#### 7.4 **Exception Handling**
   - **Purpose:**
     - Handle runtime errors gracefully.
     - Maintain normal application flow.
   - **Types of Exceptions:**
     - **Checked Exceptions:** Must be handled at compile-time (e.g., `IOException`).
     - **Unchecked Exceptions:** Occur at runtime, not required to be handled (e.g., `NullPointerException`).
     - **Errors:** Serious problems not meant to be caught (e.g., `OutOfMemoryError`).
   - **Handling Exceptions:**
     - **try-catch block:** 
       ```java
       try {
           // Code that might throw an exception
       } catch (ExceptionType e) {
           // Handle exception
       }
       ```
     - **finally block:** Always executed, used for cleanup.
     - **throw and throws:**
       - `throw`: Used to explicitly throw an exception.
       - `throws`: Declares an exception in the method signature.
     - **Custom Exceptions:**
       - Extend `Exception` or `RuntimeException` class.
       - Example:
         ```java
         class MyException extends Exception {
             public MyException(String message) {
                 super(message);
             }
         }
         ```

#### 7.5 **Annotations**
   - **Definition:**
     - Metadata for classes, methods, variables, etc.
     - Provide information to the compiler or runtime.
   - **Built-in Annotations:**
     - `@Override`: Indicates a method overrides a superclass method.
     - `@Deprecated`: Marks a method as deprecated.
     - `@SuppressWarnings`: Suppresses compiler warnings.
   - **Custom Annotations:**
     - Define using `@interface`.
     - Example:
       ```java
       @interface MyAnnotation {
           String value();
       }
       ```
   - **Retention and Target:**
     - **Retention Policy:** Specifies how long annotations are retained (`SOURCE`, `CLASS`, `RUNTIME`).
     - **Target:** Specifies where an annotation can be applied (e.g., `TYPE`, `METHOD`).

This detailed breakdown should help you structure your notes for each of these key OOP concepts.

Here’s a breakdown for the section on **Design Principles and Patterns** in your OOP notes:

### 8. **Design Principles and Patterns**

#### **8.1 SOLID Principles**
- **S**ingle Responsibility Principle (SRP): 
  - *Definition*: A class should have only one reason to change, meaning it should only have one job or responsibility.
  - *Example*: A class `InvoicePrinter` should only handle printing the invoice, not processing payments.
  
- **O**pen/Closed Principle (OCP): 
  - *Definition*: Software entities (classes, modules, functions, etc.) should be open for extension but closed for modification.
  - *Example*: Using interfaces or abstract classes to allow new functionality through inheritance without altering existing code.
  
- **L**iskov Substitution Principle (LSP): 
  - *Definition*: Objects of a superclass should be replaceable with objects of a subclass without affecting the correctness of the program.
  - *Example*: If class `Bird` has a method `fly()`, a subclass `Penguin` should not inherit `fly()` because it can’t fly. This would break LSP.
  
- **I**nterface Segregation Principle (ISP): 
  - *Definition*: A client should not be forced to depend on interfaces it does not use.
  - *Example*: Instead of one large interface `Animal`, create smaller interfaces like `IFly`, `ISwim`, and `IWalk`.
  
- **D**ependency Inversion Principle (DIP): 
  - *Definition*: High-level modules should not depend on low-level modules; both should depend on abstractions. Abstractions should not depend on details. Details should depend on abstractions.
  - *Example*: Use interfaces or abstract classes to decouple higher-level components from low-level implementation details.

#### **8.2 Common Design Patterns**
- **Singleton Pattern**:
  - *Definition*: Ensures that a class has only one instance and provides a global point of access to it.
  - *Usage*: Useful in scenarios where exactly one object is needed to coordinate actions across the system (e.g., database connection).
  - *Example*:
    ```java
    public class Singleton {
        private static Singleton instance;
        private Singleton() {}
        public static Singleton getInstance() {
            if (instance == null) {
                instance = new Singleton();
            }
            return instance;
        }
    }
    ```

- **Factory Pattern**:
  - *Definition*: Provides an interface for creating objects in a superclass, but allows subclasses to alter the type of objects that will be created.
  - *Usage*: Useful when the exact type of object to create is determined at runtime.
  - *Example*:
    ```java
    public abstract class Shape {
        abstract void draw();
    }
    public class Circle extends Shape {
        void draw() { System.out.println("Drawing Circle"); }
    }
    public class Square extends Shape {
        void draw() { System.out.println("Drawing Square"); }
    }
    public class ShapeFactory {
        public Shape getShape(String shapeType) {
            if (shapeType.equals("CIRCLE")) {
                return new Circle();
            } else if (shapeType.equals("SQUARE")) {
                return new Square();
            }
            return null;
        }
    }
    ```

- **Observer Pattern**:
  - *Definition*: Defines a one-to-many dependency between objects so that when one object changes state, all its dependents are notified and updated automatically.
  - *Usage*: Commonly used in implementing distributed event-handling systems.
  - *Example*:
    ```java
    import java.util.ArrayList;
    import java.util.List;

    interface Observer {
        void update(String message);
    }
    class ConcreteObserver implements Observer {
        private String name;
        ConcreteObserver(String name) { this.name = name; }
        public void update(String message) {
            System.out.println(name + " received: " + message);
        }
    }
    class Subject {
        private List<Observer> observers = new ArrayList<>();
        public void addObserver(Observer observer) {
            observers.add(observer);
        }
        public void notifyObservers(String message) {
            for (Observer observer : observers) {
                observer.update(message);
            }
        }
    }
    ```

#### **8.3 Example: Using Design Patterns in Java**
- **Scenario**: Implementing a notification system where multiple components (e.g., email, SMS, and push notifications) need to be updated when an event occurs.
- **Design Choice**: Use the **Observer Pattern** to notify different components of an event.
  - **Implementation**:
    1. Create an `EventManager` class to manage observers.
    2. Define `Observer` interfaces for each notification type (e.g., `EmailNotifier`, `SMSNotifier`).
    3. Implement concrete classes for each notifier.
    4. When an event occurs, `EventManager` notifies all registered observers.

This section provides an overview of essential design principles and patterns, along with examples to illustrate their application in Java.

Here’s how you can structure your notes for the "Practical Applications" section:

### 9. **Practical Applications**

#### 9.1 **Real-world Examples**
   - **Banking System**: 
     - **Classes**: Account, Customer, Transaction
     - **OOP Concepts Used**: 
       - **Encapsulation**: Customer details are private and accessed through methods.
       - **Inheritance**: Different types of accounts (Savings, Checking) inherit from a base Account class.
       - **Polymorphism**: Overriding methods for specific account types.
       - **Abstraction**: Interfaces for transaction processing.
   - **E-commerce Platform**: 
     - **Classes**: Product, ShoppingCart, Order, Payment
     - **OOP Concepts Used**:
       - **Encapsulation**: User data and payment details are private.
       - **Inheritance**: Different product types extend a common Product class.
       - **Polymorphism**: Payment processing using different payment methods.
       - **Abstraction**: Interfaces for payment gateways.
   - **Game Development**:
     - **Classes**: Player, Enemy, GameItem, Weapon
     - **OOP Concepts Used**:
       - **Encapsulation**: Player health and inventory managed privately.
       - **Inheritance**: Different enemies inherit from a base Enemy class.
       - **Polymorphism**: Different attack methods for various weapons.
       - **Abstraction**: Abstract classes for generic game items.

#### 9.2 **Best Practices**
   - **Use Encapsulation to Protect Data**: Always keep data fields private and provide public getters and setters to control access.
   - **Favor Composition Over Inheritance**: Use composition to combine behavior rather than creating deep inheritance trees.
   - **Keep Methods and Classes Small and Focused**: Each class should have a single responsibility; each method should perform one task.
   - **Adhere to the SOLID Principles**: Follow these design principles to write more maintainable and flexible code.
   - **Write Clean, Readable Code**: Use meaningful names for classes, methods, and variables. Comment code where necessary.

#### 9.3 **Common Pitfalls and How to Avoid Them**
   - **Overusing Inheritance**:
     - **Problem**: Can lead to a fragile system where changes in the base class affect all subclasses.
     - **Solution**: Consider using interfaces or composition instead.
   - **Ignoring Encapsulation**:
     - **Problem**: Directly exposing fields can lead to unintended modifications and a lack of control.
     - **Solution**: Always use private fields with public getters and setters.
   - **Failing to Use Polymorphism**:
     - **Problem**: Leads to code that is less flexible and harder to extend.
     - **Solution**: Use method overriding and interfaces to allow for more flexible and reusable code.
   - **Not Following Naming Conventions**:
     - **Problem**: Makes the code harder to read and maintain.
     - **Solution**: Follow standard Java naming conventions (camelCase for variables and methods, PascalCase for classes).
   - **Creating Large, Monolithic Classes**:
     - **Problem**: Classes become too complex and difficult to manage.
     - **Solution**: Break down large classes into smaller, more manageable ones, each with a single responsibility.

This outline will help you cover the practical aspects of OOP in Java, with a focus on how these concepts are applied in real-world scenarios, best practices for writing effective OOP code, and common mistakes to watch out for.

