# Objective-C-basics

# Object-Oriented Programming Guide

## Table of Contents
1. [Introduction to OOP](#introduction-to-oop)
2. [Basic Concepts](#basic-concepts)
3. [Defining Classes and Objects](#defining-classes-and-objects)
4. [Encapsulation](#encapsulation)
5. [Inheritance](#inheritance)
6. [Polymorphism](#polymorphism)
7. [Abstraction](#abstraction)
8. [Examples](#examples)
9. [Conclusion](#conclusion)

## Introduction to OOP

Object-Oriented Programming (OOP) is a programming paradigm based on the concept of "objects", which can contain data and code: data in the form of fields, and code, in the form of procedures.

OOP was developed to overcome the limitations of procedural programming. It aims to implement real-world entities like inheritance, hiding, polymorphism, etc. in programming.

### History of OOP
OOP concepts began with the language Simula in the mid-1960s and further evolved with Smalltalk in the 1970s. Modern OOP languages include Java, C++, Python, and C#【12:0†source】【12:1†source】.

## Basic Concepts

### Objects
An object is a self-contained component that contains properties and methods needed to make a certain type of data useful. Each object is an instance of a class.

### Classes
A class is a blueprint or prototype from which objects are created. It defines a datatype by bundling data and methods that work on the data into one single unit.

### Encapsulation
Encapsulation is the mechanism of hiding the internal details of an object from the outside world and only exposing what is necessary. This is done using access specifiers such as private, protected, and public.

### Inheritance
Inheritance allows a class to inherit properties and behavior from another class. The class that inherits is called a subclass, and the class from which properties are inherited is called a superclass.

### Polymorphism
Polymorphism allows methods to do different things based on the object it is acting upon, even though they share the same name. There are two types of polymorphism: compile-time (method overloading) and runtime (method overriding).

### Abstraction
Abstraction is the concept of hiding the complex implementation details and showing only the necessary features of an object. It is achieved using abstract classes and interfaces.

## Defining Classes and Objects

### Creating a Class

```csharp
class Employee
{
    private int empID;
    private string name;

    public int EmployeeID
    {
        get { return empID; }
        set { empID = value; }
    }

    public string Name
    {
        get { return name; }
        set { name = value; }
    }

    public void Display()
    {
        Console.WriteLine($"Employee ID: {empID}, Name: {name}");
    }
}
```

### Creating an Object

```csharp
Employee emp = new Employee();
emp.EmployeeID = 1;
emp.Name = "John Doe";
emp.Display();
```

## Encapsulation

Encapsulation is implemented by making class fields private and providing public methods to access and update the values of these fields.

### Example

```csharp
class Account
{
    private double balance;

    public double Balance
    {
        get { return balance; }
        set 
        { 
            if (value >= 0)
                balance = value; 
        }
    }

    public void Deposit(double amount)
    {
        if (amount > 0)
            balance += amount;
    }

    public void Withdraw(double amount)
    {
        if (amount > 0 && amount <= balance)
            balance -= amount;
    }
}
```

## Inheritance

Inheritance allows a new class to inherit the properties and methods of an existing class.

### Example

```csharp
class Animal
{
    public void Eat()
    {
        Console.WriteLine("Eating...");
    }
}

class Dog : Animal
{
    public void Bark()
    {
        Console.WriteLine("Barking...");
    }
}

// Usage
Dog dog = new Dog();
dog.Eat();
dog.Bark();
```

## Polymorphism

Polymorphism allows methods to have the same name but behave differently based on the object calling them.

### Example

```csharp
class Shape
{
    public virtual void Draw()
    {
        Console.WriteLine("Drawing a shape...");
    }
}

class Circle : Shape
{
    public override void Draw()
    {
        Console.WriteLine("Drawing a circle...");
    }
}

class Rectangle : Shape
{
    public override void Draw()
    {
        Console.WriteLine("Drawing a rectangle...");
    }
}

// Usage
Shape shape;

shape = new Circle();
shape.Draw();  // Output: Drawing a circle...

shape = new Rectangle();
shape.Draw();  // Output: Drawing a rectangle...
```

## Abstraction

Abstraction is implemented using abstract classes and interfaces.

### Abstract Class Example

```csharp
abstract class Animal
{
    public abstract void MakeSound();

    public void Sleep()
    {
        Console.WriteLine("Sleeping...");
    }
}

class Dog : Animal
{
    public override void MakeSound()
    {
        Console.WriteLine("Barking...");
    }
}

// Usage
Dog dog = new Dog();
dog.MakeSound();  // Output: Barking...
dog.Sleep();      // Output: Sleeping...
```

### Interface Example

```csharp
interface IAnimal
{
    void MakeSound();
}

class Dog : IAnimal
{
    public void MakeSound()
    {
        Console.WriteLine("Barking...");
    }
}

// Usage
IAnimal animal = new Dog();
animal.MakeSound();  // Output: Barking...
```

## Examples

### Creating Classes and Objects

```csharp
class Person
{
    private string name;
    private int age;

    public string Name
    {
        get { return name; }
        set { name = value; }
    }

    public int Age
    {
        get { return age; }
        set { age = value; }
    }

    public void Display()
    {
        Console.WriteLine($"Name: {Name}, Age: {Age}");
    }
}

// Usage
Person person = new Person();
person.Name = "Alice";
person.Age = 30;
person.Display();  // Output: Name: Alice, Age: 30
```

### Encapsulation Example

```csharp
class BankAccount
{
    private double balance;

    public double Balance
    {
        get { return balance; }
        set 
        { 
            if (value >= 0)
                balance = value; 
        }
    }

    public void Deposit(double amount)
    {
        if (amount > 0)
            balance += amount;
    }

    public void Withdraw(double amount)
    {
        if (amount > 0 && amount <= balance)
            balance -= amount;
    }
}

// Usage
BankAccount account = new BankAccount();
account.Deposit(500);
account.Withdraw(200);
Console.WriteLine(account.Balance);  // Output: 300
```

## Conclusion

Object-Oriented Programming is a powerful paradigm that helps in organizing and structuring software in a more manageable and scalable way. By understanding and applying OOP concepts such as encapsulation, inheritance, polymorphism, and abstraction, you can create robust and maintainable code.

---

Feel free to extend this guide with more examples and explanations as needed for your GitHub repository.
