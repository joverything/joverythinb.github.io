---
layout: single
title:  "Object-Oriented Programming in C#"
categories: C#
tag: [CSharp, ObjectOrientedProgramming, OOP, Programming, Coding, SoftwareDevelopment]
toc: false
author_profile: false
sidebar:
    nav: "counts"
---

# Object-Oriented Programming in C#

Object-oriented programming (OOP) is an important concept in modern programming, and C# is a great language for getting started with OOP. In this article, we'll take a look at some of the basic principles of OOP and how they apply to C#.

## What is Object-Oriented Programming?

Object-oriented programming (OOP) is a programming paradigm that focuses on objects rather than functions. An object is a collection of related data and methods that can be used to interact with the data. OOP is based on the idea that objects can be used to create models of real-world scenarios. 

For example, a bank account object could contain information about the account holder, such as their name, address, and balance. It could also contain methods for depositing money, withdrawing money, and printing a statement. 

## Principles of Object-Oriented Programming

OOP is based on a few key principles:

* **Encapsulation**: Encapsulation is the process of hiding the implementation details of a class from other classes. This allows the object to control how its data is accessed and modified. 

* **Abstraction**: Abstraction is the process of hiding the details of an object from the user. This allows the user to interact with the object without having to worry about the underlying implementation. 

* **Inheritance**: Inheritance is the process of creating a new class from an existing class. This allows the new class to inherit the properties and methods of the existing class, while also adding its own unique functionality. 

* **Polymorphism**: Polymorphism is the process of creating multiple versions of the same method. This allows the object to respond differently to the same method call depending on the context. 

## Object-Oriented Programming in C#

C# is a great language for getting started with OOP. It has support for all of the principles of OOP, as well as many features that make working with objects easier. 

### Classes and Objects

In C#, classes are used to define objects. A class is a template for an object, and it contains information about the data and methods that the object will have. 

For example, here's a class for a bank account object:

```csharp
public class BankAccount
{
    public string AccountNumber { get; set; }
    public string Name { get; set; }
    public decimal Balance { get; set; }

    public void Deposit(decimal amount)
    {
        Balance += amount;
    }

    public void Withdraw(decimal amount)
    {
        Balance -= amount;
    }

    public void PrintStatement()
    {
        Console.WriteLine("Account Number: {0}", AccountNumber);
        Console.WriteLine("Name: {0}", Name);
        Console.WriteLine("Balance: {0}", Balance);
    }
}
```

Once a class has been defined, objects can be created from it. An object is an instance of a class, and it contains the data and methods that were defined in the class. 

For example, here's how we could create a bank account object from the above class:

```csharp
BankAccount account = new BankAccount();
account.AccountNumber = "12345";
account.Name = "John Doe";
account.Balance = 1000.00m;
```

### Inheritance

Inheritance is a key feature of OOP, and it's supported in C#. A class can inherit from another class, which allows it to reuse the existing code while also adding its own unique functionality. 

For example, here's a class that inherits from the `BankAccount` class:

```csharp
public class SavingsAccount : BankAccount
{
    public decimal InterestRate { get; set; }

    public void AddInterest()
    {
        Balance += Balance * InterestRate;
    }
}
```

The `SavingsAccount` class inherits from the `BankAccount` class, so it has access to all of the data and methods from that class. It also adds its own unique data (`InterestRate`) and methods (`AddInterest()`). 

### Polymorphism

Polymorphism is another key feature of OOP, and it's supported in C#. Polymorphism allows an object to respond differently to the same method call depending on the context. 

For example, here's a class that contains a method that can be used to print a statement:

```csharp
public class PrintStatement
{
    public virtual void Print()
    {
        Console.WriteLine("Printing statement...");
    }
}
```

The `Print()` method can be overridden in a derived class, which allows the object to respond differently to the same method call:

```csharp
public class BankStatement : PrintStatement
{
    public override void Print()
    {
        Console.WriteLine("Printing bank statement...");
    }
}
```

## Conclusion

Object-oriented programming is an important concept in modern programming, and C# is a great language for getting started with OOP. In this article, we looked at some of the basic principles of OOP and how they apply to C#. 
