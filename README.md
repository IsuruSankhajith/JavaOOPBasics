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

## Introduction to OOP

Object-Oriented Programming is a paradigm that provides a way to structure programs using objects. The core principles of OOP are Encapsulation, Inheritance, Polymorphism, and Abstraction.

## Classes and Objects

- **Class**: Blueprint for creating objects. It defines properties and behaviors (methods).
- **Object**: Instance of a class.

Example:

```java
class Car {
    String model;
    int year;
    
    void startEngine() {
        System.out.println("Engine started!");
    }
}

public class Main {
    public static void main(String[] args) {
        Car car = new Car();
        car.startEngine();
    }
}
