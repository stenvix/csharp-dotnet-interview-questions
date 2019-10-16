# C# / .NET interview questions (with answers)

## Table of Contents

- [Basic Concepts](#basic-concepts)
    - [What is C#?](#1.-what-is-c#)
    - [What is an Object and a Class?](#2.-what-is-an-object-and-a-class)
    - [What are the fundamental OOP concepts?](#3.-what-are-the-fundamental-OOP-concepts)
     - [What is an Interface?](#4.-What-is-an-interface?)
- [Entity Framework](#entity-framework)
    - [What is Entity Framework?](#1-what-is-entity-framework)
## Preface
TODO

## Basic Concepts

### 1. What is C#?

<details>
<summary>Answer</summary>

C# is a computer programming language. C# was created by Microsoft in 2000 to provide a modern general-purpose programming language that can be used to develop all kind of software targeting various platforms including Windows, Web, and Mobile using just one programming language. Today, C# is one of the most popular programming languages in the world. Millions of software developers use C# to build all kind of software. 
</details>

### 2. What is an Object and a Class?

<details>
<summary>Answer</summary>

A **Class** is an encapsulation of properties and methods that are used to represent a real-time entity. It is a data structure that brings all the instances together in a single unit.

An **Object** in an instance of a Class. Technically, it is just a block of memory allocated that can be stored in the form of Variables, Array or a Collection.
</details>

### 3.  What are the fundamental OOP concepts?
<details>
<summary>Answer</summary>

- **Encapsulation** – The Internal representation of an object is hidden from the view outside object’s definition. Only the required information can be accessed whereas the rest of the data implementation is hidden.
- **Abstraction** – It is a process of identifying the critical behavior and data of an object and eliminating the irrelevant details.
- **Inheritance** – It is the ability to create new classes from another class. It is done by accessing, modifying and extending the behavior of objects in the parent class.
- **Polymorphism** – The name means, one name, many forms. It is achieved by having multiple methods with the same name but different implementations.
</details>

### 4. What is an Interface?
<details>
<summary>Answer</summary>

An **Interface** is a class with no implementation. The only thing that it contains is the declaration of methods, properties, and events.
</details>

### 5. What be the output of the following code?

```
class A
{
    public virtual void Say()
    {
        Console.WriteLine("A");
    }
}

class B: A
{
    public override void Say()
    {
        Console.WriteLine("B");
    }
}

class C:B
{
    public new void Say()
    {
        Console.WriteLine("C");
    }
}

static void Main(string[] args)
{
    A x = new C();
    x.Say();
}

```

<details>
<summary>Answer</summary>

The output would be "**B**"

**override**: virtual keyword must be defined to override the method. The method using override keyword that regardless of reference type(reference of base class or derived class) if it is instantiated with base class, the method of base class runs. Otherwise, the method of derived class runs.

**new**: if the keyword is used by a method, unlike override keyword, the reference type is important. If it is instantiated with derived class and the reference type is base class, the method of base class runs. If it is instantiated with derived class and the reference type is derived class, the method of derived class runs. Namely, it is contrast of override keyword. En passant, if you forget or omit to add new keyword to the method, the compiler behaves by default as new keyword is used.

</details>

## Entity Framework

### 1. What is Entity Framework?

<details>
<summary>Answer</summary>

**ADO.NET Entity Framework** is an ORM framework that empowers developers to work with various relational databases like SQL Server, Oracle, DB2, MYSQL etc. It allows developers to deal with data as objects or entities. Using the Entity Framework, developers issue queries using LINQ, then retrieve and manipulate data as strongly typed objects using C# or VB.NET Framework.

</details>

### 2. What is the difference between Entity Framework and `ADO.NET`?

<details>
<summary>Answer</summary>

| ADO.NET       | Entity Framework
| ------------- |:-------------:| -----:|
| ADO.NET is faster. | "Entity Framework will be around the ADO.NET, which means ADO.NET is faster than Entity Framework." |
| We need to write so much code to talk to database. | Easy to use. As an Entity Framework will talk to database without much code involved. |
| Performance is better than Entity Framework. | Performance is not good compared to ADO.NET. |

</details>

### 3. What other O/RMs you can use with .NET based applications?

<details>
<summary>Answer</summary>

- Entity Framework 6.x
- Entity Framework Core
- Dapper
- N Hibernate

</details>

### 4. What is Micro O/RMs?

//TODO

### 5. What is SQL injection attack?

<details>
<summary>Answer</summary>

A SQL injection attack is an attack mechanism used by hackers to steal sensitive information from the database of an organization. It is the application layer (means front-end) attack which takes benefit of inappropriate coding of our applications that allows a hacker to insert SQL commands into your code that is using SQL statement.

SQL Injection arises since the fields available for user input allow SQL statements to pass through and query the database directly. SQL Injection issue is a common issue with an ADO.NET Data Services query.

</details>

### 6. How to handle SQL injection attacks in Entity Framework?

<details>
<summary>Answer</summary>

Entity Framework is injection safe since it always generates parameterized SQL commands which help to protect our database against SQL Injection.

A SQL injection attack can be made in Entity SQL syntax by providing some malicious inputs that are used in a query and in parameter names. To avoid this one, you should never combine user inputs with Entity SQL command text.

</details>

### 7. What are various approaches to domain modeling in Entity Framework?

<details>
<summary>Answer</summary>

**Code first**

Code first is the domain modelling approach in Entity Framework. It enables you to describe a model by using C# or VB.NET classes and then create database from these classes. These classes are called POCO classes.

This approach enables us to work entirely in an object-oriented direction, and not worry about the structure of the database. This abstraction allow us to make a more logically and flexible application that focuses on the behaviour of the application rather than the database generated by it.

Advantages of Code First
1. It is very popular approach since it allow you to make a more logically and flexible application.
2. It provides full control over the code since there is no auto generated code which is hard to modify.
3. In this approach, your code defines only the database mappings and EF will handle creation of database with its relations.
4. Manual changes to database schema is not preferable because your code defines the database.
5. You can also use Code first to map your model to an existing database.

**Model First**

Model first is the domain modelling approach in Entity Framework. It enables you to create model’s Entities, relationships, and inheritance hierarchies on the design surface of empty model (.edmx file) by using entity designer and then create database from it. This approach is adopted by the architect and solution lead developers.

In Model First approach, while creating Entity Data Model, you must select the option “Empty Model” instead of "Generate from database" option. 

Advantage of Model First
1. It is good if you like to visualize the structure of the data in the application or you don't like writing code or SQL since it will generate for you.
2. In this approach you have no much control over your entities (auto generated code which is hard to modify) and database. In this way it is rarely used but for small easy projects this approach will be very productive.
3. To add extra features in POCO entities you must either T4 modify template or use partial classes.
4. Manual changes to database schema is not preferable because your model defines the database.

**Database First**

Database first is the domain modelling approach in Entity Framework. It enables you to create model from an existing database (like SQL Server, Oracle, DB2 etc.). This approach reduces the amount of code that we need to write since it automatically generates code. But it also limits us to work with the structure of the generated code.

Advantage of Database First
1. Very popular if you have Database designed by DBAs, developed separately or if you have existing Database.
2. EDM wizard creates entities, relationships, and inheritance hierarchies for you. After modification of mapping, you can also generate POCO class entities.
3. To add extra features in POCO entities you must either T4 modify template or use partial classes.
4. Manual changes to the database are possible because the database defines your domain model. You can always update model from database.

</details>