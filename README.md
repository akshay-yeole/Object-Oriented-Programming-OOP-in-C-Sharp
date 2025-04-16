
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

### ✅ Benefits of Encapsulation

- Protects internal object state.
- Enables validation logic.
- Increases modularity.
- Improves maintainability and flexibility.

### 💻 Example

```csharp
public class BankAccount
{
    private decimal balance;

    public decimal GetBalance()
    {
        return balance;
    }

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

### ✅ Benefits of Abstraction

- Simplifies code interaction.
- Reduces complexity.
- Enhances security and modularity.
- Promotes loose coupling.

### 💻 Example 1: Abstract Class

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

    public Circle(double radius)
    {
        Radius = radius;
    }

    public override double GetArea()
    {
        return Math.PI * Radius * Radius;
    }
}

// Usage
var circle = new Circle(5);
circle.Display();  // Output: Area: 78.54
```

### 💻 Example 2: Interface

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
    public void Eat()
    {
        Console.WriteLine("Eating...");
    }
}

public class Dog : Animal
{
    public void Bark()
    {
        Console.WriteLine("Barking...");
    }
}

// Usage
Dog dog = new Dog();
dog.Eat();  // From base class
dog.Bark(); // From derived class
```

### ✅ Key Points

- Use `:` to inherit from a base class.
- Promotes code reuse and organization.
- C# supports **single inheritance**.
- Public and protected members are accessible in derived classes.

**Hierarchy Example:**

```
Animal
  └── Dog
```

---

# 🧬 Types of Inheritance in C#

C# supports several types of inheritance, allowing one class to derive from another. This promotes code reusability and organized software design.

> ⚠️ Note: C# supports **single inheritance** only for classes, but **multiple inheritance** is possible using interfaces.

---

## 1. 🔹 Single Inheritance

A class inherits from one base class.

### 💻 Example:

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
dog.Eat();  // Inherited
dog.Bark(); // Own method
```

---

## 2. 🔹 Multilevel Inheritance

A class is derived from a class which is also derived from another class.

### 💻 Example:

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

## 3. 🔹 Hierarchical Inheritance

Multiple classes inherit from the same base class.

### 💻 Example:

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

## 4. 🔹 Multiple Inheritance (via Interfaces)

C# does not support multiple class inheritance directly. However, multiple interfaces can be implemented by a single class.

### 💻 Example:

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

## 5. 🔹 Hybrid Inheritance

Hybrid inheritance is a combination of two or more types of inheritance. Though C# doesn’t support hybrid inheritance through classes due to ambiguity (diamond problem), it can be mimicked using interfaces.

---

## ✅ Summary Table

| Type         | Supported in C# | Method               |
|--------------|------------------|----------------------|
| Single       | ✅               | Classes              |
| Multilevel   | ✅               | Classes              |
| Hierarchical | ✅               | Classes              |
| Multiple     | ✅               | Interfaces           |
| Hybrid       | ⚠️ (Limited)     | Interfaces & Classes |

---

## 📌 Note on Diamond Problem

In languages that support multiple class inheritance (like C++), a class may inherit from two classes that share a common base class, leading to ambiguity.  
C# avoids this issue by not supporting multiple class inheritance, encouraging interface usage instead.

---

## 🎭 Polymorphism

**Polymorphism** allows objects to be treated as instances of their parent class rather than their actual class, enabling method overriding and flexibility.

🔜 Full section on Polymorphism coming soon with:

- ✅ Clear explanations  
- 💡 Real-world examples  
- 🧑‍💻 Best practices  

---

## 📂 Upcoming Content

We’re working on adding more practical OOP sections:

- 🎭 Full Polymorphism examples
- 🏗 SOLID Principles
- 🧪 Unit Testing with OOP
- 🔁 Composition vs Inheritance

Stay tuned!

---

## 📧 Contact

Have feedback or want to collaborate?

- 📫 Email: [akshay-yeole@outlook.com](mailto:akshay-yeole@outlook.com)  
- 💼 LinkedIn: [Akshay Yeole](https://www.linkedin.com/in/akshayyeole)

Feel free to open an issue or pull request if you'd like to contribute or suggest improvements.

---

## ⭐️ Support the Project

If you find this project helpful:

- Star ⭐ the repository
- Share with fellow C# learners or developers

Your support inspires continuous improvement and learning resources!

---

> Made with 💻 by Akshay Yeole
