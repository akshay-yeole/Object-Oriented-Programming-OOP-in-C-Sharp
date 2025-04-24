
# 👨‍💻 Object-Oriented Programming (OOP) in C#

Welcome to the **Object-Oriented Programming (OOP) in C#** repository by **Akshay Yeole**.  
This beginner-friendly resource helps you understand the four core principles of OOP in C#:

- 🔒 Encapsulation  
- 🧬 Inheritance  
- 🎭 Polymorphism  
- 🧊 Abstraction  

---

## 🔒 Encapsulation

**Encapsulation** means bundling data (fields) and methods that operate on that data into a single unit — usually a class. It also restricts direct access to some of the object’s components.

### ✅ Benefits

- Protects internal object state.
- Enables validation logic.
- Increases modularity.
- Improves maintainability and flexibility.

### 💻 Example

```csharp
public class BankAccount
{
    private decimal balance;

    public decimal GetBalance() => balance;

    public void Deposit(decimal amount)
    {
        if (amount > 0)
        {
            balance += amount;
        }
    }
}
```

---

## 🧊 Abstraction

**Abstraction** is about exposing only essential features while hiding internal implementation details.

### ✅ Benefits

- Simplifies code interaction.
- Reduces complexity.
- Enhances security and modularity.
- Promotes loose coupling.

### 💻 Example: Abstract Class

```csharp
public abstract class Shape
{
    public abstract double GetArea();

    public void Display()
    {
        Console.WriteLine($"Area: {GetArea()}");
    }
}

public class Circle : Shape
{
    public double Radius { get; set; }

    public Circle(double radius) => Radius = radius;

    public override double GetArea() => Math.PI * Radius * Radius;
}

// Usage
var circle = new Circle(5);
circle.Display();  // Output: Area: 78.54
```

### 💻 Example: Interface

```csharp
public interface IShape
{
    double GetArea();
    void Display();
}

public class Rectangle : IShape
{
    public double Width { get; set; }
    public double Height { get; set; }

    public Rectangle(double width, double height)
    {
        Width = width;
        Height = height;
    }

    public double GetArea() => Width * Height;

    public void Display() => Console.WriteLine($"Area: {GetArea()}");
}

// Usage
var rectangle = new Rectangle(4, 6);
rectangle.Display();  // Output: Area: 24
```

---

## 🧬 Inheritance

**Inheritance** enables a class (child/derived) to inherit properties and methods from another class (parent/base).

### 💡 Syntax

```csharp
public class Animal
{
    public void Eat() => Console.WriteLine("Eating...");
}

public class Dog : Animal
{
    public void Bark() => Console.WriteLine("Barking...");
}

// Usage
var dog = new Dog();
dog.Eat();
dog.Bark();
```

### ✅ Key Points

- Use `:` to inherit from a base class.
- Promotes code reuse and organization.
- C# supports **single inheritance**.
- Public and protected members are accessible in derived classes.

### 📊 Hierarchy

```
Animal
  └── Dog
```

---

## 🧬 Types of Inheritance in C#

C# supports several types of inheritance. While **classes** support only single inheritance, **interfaces** allow multiple inheritance.

---

### 1. 🔹 Single Inheritance

A class inherits from one base class.

```csharp
public class Animal
{
    public void Eat() => Console.WriteLine("Eating...");
}

public class Dog : Animal
{
    public void Bark() => Console.WriteLine("Barking...");
}

// Usage
var dog = new Dog();
dog.Eat();
dog.Bark();
```

---

### 2. 🔹 Multilevel Inheritance

A class is derived from a class that is also derived from another class.

```csharp
public class Animal
{
    public void Eat() => Console.WriteLine("Eating...");
}

public class Mammal : Animal
{
    public void Walk() => Console.WriteLine("Walking...");
}

public class Human : Mammal
{
    public void Speak() => Console.WriteLine("Speaking...");
}

// Usage
var human = new Human();
human.Eat();
human.Walk();
human.Speak();
```

---

### 3. 🔹 Hierarchical Inheritance

Multiple classes inherit from the same base class.

```csharp
public class Animal
{
    public void Eat() => Console.WriteLine("Eating...");
}

public class Dog : Animal
{
    public void Bark() => Console.WriteLine("Barking...");
}

public class Cat : Animal
{
    public void Meow() => Console.WriteLine("Meowing...");
}

// Usage
var dog = new Dog();
dog.Eat();
dog.Bark();

var cat = new Cat();
cat.Eat();
cat.Meow();
```

---

### 4. 🔹 Multiple Inheritance (via Interfaces)

C# doesn't support multiple class inheritance directly but allows multiple interfaces.

```csharp
public interface IWork
{
    void DoWork();
}

public interface IStudy
{
    void DoStudy();
}

public class Person : IWork, IStudy
{
    public void DoWork() => Console.WriteLine("Working...");
    public void DoStudy() => Console.WriteLine("Studying...");
}

// Usage
var person = new Person();
person.DoWork();
person.DoStudy();
```

---

### 5. 🔹 Hybrid Inheritance

A combination of two or more inheritance types. Achievable using interfaces in C#.

---

## ✅ Summary Table

| Type         | Supported | Implementation         |
|--------------|-----------|------------------------|
| Single       | ✅        | Classes                |
| Multilevel   | ✅        | Classes                |
| Hierarchical | ✅        | Classes                |
| Multiple     | ✅        | Interfaces             |
| Hybrid       | ⚠️ Limited | Classes + Interfaces  |

---

### 📌 Note on Diamond Problem

C# avoids the diamond problem by not allowing multiple class inheritance. Instead, it encourages the use of interfaces.

---

## 🎭 Polymorphism

**Polymorphism** allows objects to be treated as instances of their parent class rather than their actual class.
Poly means many and morph means behaviours.

Types of polymorphism :
1. static polymorphism | Early Binding
2. dynamic polymorphism | Late Binding

We can implement polymorphism by overloading, overriding and hiding data.

Early Binding
Earli binding is a type of polymorphism in object-oriented programming that is resolved during the compilation of the program. It allows methods to be overloaded based on their parameter types or numbers, enabling different implementations of the same method name within a class.

Example :
method overloading is a classic example of compile-time polymorphism:
```c#
public class Calculator
{
    // Method with two parameters
    public int Add(int a, int b)
    {
        return a + b;
    }

    // Overloaded method with three parameters
    public int Add(int a, int b, int c)
    {
        return a + b + c;
    }
}

class Program
{
    static void Main(string[] args)
    {
        Calculator calc = new Calculator();
        
        Console.WriteLine(calc.Add(5, 10)); // Calls the method with two parameters
        Console.WriteLine(calc.Add(5, 10, 15)); // Calls the method with three parameters
    }
}
```
In this example, the Add method is overloaded, and the correct implementation is chosen based on the number of arguments at compile time. This is distinct from runtime polymorphism, which is resolved during program execution. Let me know if you need more examples!

Late Binding : 
Late binding is a type of polymorphism in object-oriented programming that is resolved during the execution of the program. It allows a method to be overridden in a derived class, enabling different behavior based on the runtime type of the object.

Example :
method overriding is a typical example of runtime polymorphism achieved using inheritance and the virtual, override, and base keywords:
```c#
public class Animal
{
    // Virtual method in the base class
    public virtual void MakeSound()
    {
        Console.WriteLine("Animal makes a sound.");
    }
}

public class Dog : Animal
{
    // Overriding the virtual method
    public override void MakeSound()
    {
        Console.WriteLine("Dog barks.");
    }
}

public class Cat : Animal
{
    // Overriding the virtual method
    public override void MakeSound()
    {
        Console.WriteLine("Cat meows.");
    }
}

class Program
{
    static void Main(string[] args)
    {
        Animal myAnimal;

        // Runtime polymorphism in action
        myAnimal = new Dog();
        myAnimal.MakeSound(); // Output: Dog barks.

        myAnimal = new Cat();
        myAnimal.MakeSound(); // Output: Cat meows.

        Console.ReadLine();
    }
}

```
Explanation:
Virtual Method: The base class Animal declares a method MakeSound as virtual, allowing it to be overridden.

Override Method: Derived classes Dog and Cat override MakeSound to provide their own implementation.

Runtime Behavior: At runtime, the method to be executed is determined based on the actual type of the object (Dog or Cat), not the declared type (Animal).

This dynamic behavior is essential for creating flexible and extensible systems. It enables method calls to be dynamically dispatched, depending on the object's runtime type. Let me know if you'd like more clarification!

Method Hiding : 
Method Hiding occurs when a derived class defines a method with the same name as a method in the base class but does not override it. Instead, it hides the base class method, and the behavior depends on the type of the reference used to call the method. The new keyword is used to explicitly indicate that the method in the derived class is intended to hide the method in the base class.

Example:
```c#
using System;

public class BaseClass
{
    public void Display()
    {
        Console.WriteLine("This is the Display method in the BaseClass.");
    }
}

public class DerivedClass : BaseClass
{
    // Method hiding
    public new void Display()
    {
        Console.WriteLine("This is the Display method in the DerivedClass.");
    }
}

class Program
{
    static void Main(string[] args)
    {
        BaseClass baseObj = new BaseClass();
        baseObj.Display(); // Calls BaseClass method

        DerivedClass derivedObj = new DerivedClass();
        derivedObj.Display(); // Calls DerivedClass method

        // Base class reference to a derived class object
        BaseClass polymorphicObj = new DerivedClass();
        polymorphicObj.Display(); // Calls BaseClass method (hiding is not polymorphic)

        Console.ReadLine();
    }
}

```
Explanation:
BaseClass Method:

The BaseClass contains a Display method.

DerivedClass Method:

The DerivedClass defines its own Display method and uses the new keyword to hide the base class method.

Behavior:

When calling Display using a DerivedClass reference, the derived class method is executed.

However, if a base class reference is used to call Display (even when it points to a DerivedClass object), the base class method is called.

🔜 Coming soon with:

- ✅ Clear explanations  
- 💡 Real-world examples  
- 🧑‍💻 Best practices  

---

## 📂 Upcoming Content

- 🏗 SOLID Principles
- 🧪 Unit Testing with OOP
- 🔁 Composition vs Inheritance

---

## 📧 Contact

- 📫 Email: [akshay-yeole@outlook.com](mailto:akshay-yeole@outlook.com)  
- 💼 LinkedIn: [Akshay Yeole](https://www.linkedin.com/in/akshayyeole)

---

## ⭐️ Support

If this helped you:

- Star ⭐ the repo
- Share with other C# learners

> Made with 💻 by Akshay Yeole
