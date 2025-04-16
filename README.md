
# 👨‍💻 Object-Oriented Programming (OOP) in C# – Akshay Yeole

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

🔜 Coming soon with:

- ✅ Clear explanations  
- 💡 Real-world examples  
- 🧑‍💻 Best practices  

---

## 📂 Upcoming Content

- 🎭 Polymorphism in depth
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
