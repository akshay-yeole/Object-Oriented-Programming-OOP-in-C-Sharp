
# 👨‍💻 Object-Oriented Programming (OOP) in C# 
![GitHub stars](https://img.shields.io/github/stars/akshay-yeole/Object-Oriented-Programming-OOP-in-C-Sharp)

Welcome to the **Object-Oriented Programming (OOP) in C#** repository by **Akshay Yeole**.  
This beginner-friendly resource helps you understand the four core principles of OOP in C#:

- 🔒 Encapsulation  
- 🧬 Inheritance  
- 🎭 Polymorphism  
- 🧊 Abstraction  

---

## Class
A class in C# is a fundamental building block of object-oriented programming (OOP). It serves as a blueprint or template to define the properties and behaviors of objects. Essentially, a class encapsulates data (fields) and functions (methods) that operate on the data, promoting modularity, reusability, and organized code structure.

Key Features of a Class:
Fields: Variables that store the data of the class.

Properties: Special methods to access and manipulate fields in a controlled way.

Methods: Functions that define the behavior or actions of the class.

Constructors: Special methods to initialize objects of the class.

Access Modifiers: Define the visibility of members (e.g., public, private, protected).

Syntax Example:
Here’s a basic example of a C# class:

```c#
public class Car
{
    // Fields
    private string brand;
    private int speed;

    // Constructor
    public Car(string carBrand, int carSpeed)
    {
        brand = carBrand;
        speed = carSpeed;
    }

    // Property
    public string Brand
    {
        get { return brand; }
        set { brand = value; }
    }

    // Method
    public void Drive()
    {
        Console.WriteLine($"{brand} is driving at {speed} km/h.");
    }
}

```
Usage:
You can create objects and use their methods like this:
```c#
Car myCar = new Car("Tesla", 120);
myCar.Drive(); // Output: Tesla is driving at 120 km/h.
```
Notes:
Classes can be extended using inheritance, meaning one class can derive from another.

Static classes are used when you don’t need to create instances of a class.

## Partial Class
In C#, a partial class allows you to split the definition of a class into multiple files. This can be especially useful when working on large projects with lengthy class definitions or when multiple developers are collaborating on the same class. The compiler combines all parts of a partial class into a single class during compilation.

### Key Features of Partial Classes:
Code Separation: Keep your code well-organized and easier to read.

Collaboration: Multiple developers can work on different parts of the same class without conflicts.

Generated Code: Useful when part of the class definition is auto-generated (e.g., in tools like Visual Studio's designer).

Syntax Example:
Here’s how partial classes work:
File 1: PartialClassPart1.cs
```c#
public partial class MyClass
{
    public void Method1()
    {
        Console.WriteLine("Method1 executed!");
    }
}

```
File 2: PartialClassPart2.cs
```c#
public partial class MyClass
{
    public void Method2()
    {
        Console.WriteLine("Method2 executed!");
    }
}

```
Usage:
```c#
MyClass obj = new MyClass();
obj.Method1();
obj.Method2();

```
Notes:
All parts of the partial class must be marked with the partial keyword.

The class must exist in the same namespace across all files.

It's only for classes, structs, or interfaces—not methods or properties.

## Partial Method
In C#, a partial method allows you to define a method signature in one part of a partial class and implement it in another part. This provides flexibility when working with auto-generated code and custom logic, as you can define methods without requiring their immediate implementation.

Key Points About Partial Methods:
Declared in Partial Classes/Structs: Partial methods must reside within a partial class or struct.

Optional Implementation: The implementation of a partial method is optional. If it's not implemented, the compiler removes it (along with any calls to it) during compilation, ensuring no performance overhead.

No Access Modifiers: Partial methods are implicitly private and cannot have access modifiers like public or protected.

Return Type: They must return void. Partial methods cannot return any value.

Syntax Example:
File 1: PartialClassPart1.cs
```c#
public partial class MyClass
{
    // Declaration of a partial method
    partial void OnStart();

    public void Start()
    {
        Console.WriteLine("Starting...");
        OnStart(); // Call the partial method
    }
}

```
File 2: PartialClassPart2.cs
```c#
public partial class MyClass
{
    // Implementation of the partial method
    partial void OnStart()
    {
        Console.WriteLine("OnStart method executed!");
    }
}
```
Usage:
```c#
MyClass obj = new MyClass();
obj.Start();
// Output:
// Starting...
// OnStart method executed!
```
If the OnStart method isn't implemented in the second file, the call to OnStart() in Start() will simply be ignored at compile time.

Benefits of Partial Methods:
Seamless integration with auto-generated code, like in tools or frameworks.

Avoids cluttering code with unused methods, as unused partial methods are removed at compile time.

Enhances modularity and collaboration on large projects.

## sealed class
In C#, a sealed class is a class that cannot be inherited by other classes. This is useful when you want to restrict the extension of a class, ensuring that no other class can derive from it. You can declare a sealed class using the sealed keyword.

```c#
sealed class MySealedClass
{
    public void DisplayMessage()
    {
        Console.WriteLine("This is a sealed class.");
    }
}

// The following will cause a compilation error because MySealedClass is sealed:
// class DerivedClass : MySealedClass { }

```

Key points about sealed classes:

A sealed class can be instantiated, but it cannot serve as a base class.

You often use sealed classes to enhance security, prevent unintended behavior from inheritance, or optimize performance by allowing certain compiler optimizations.

Structs in C# are implicitly sealed, meaning you can't inherit from a struct.

## Sealed Method
In C#, a sealed method is a method in a derived class that cannot be overridden by further derived classes. You can declare a sealed method by using the sealed keyword, which must be used alongside the override keyword.

This is typically done to prevent changes to the implementation of a method in classes that further derive from the current one.

```c#
class BaseClass
{
    public virtual void DisplayMessage()
    {
        Console.WriteLine("Message from BaseClass.");
    }
}

class DerivedClass : BaseClass
{
    public sealed override void DisplayMessage()
    {
        Console.WriteLine("Message from DerivedClass.");
    }
}

// The following will cause a compilation error because DisplayMessage is sealed:
// class FurtherDerivedClass : DerivedClass
// {
//     public override void DisplayMessage()
//     {
//         Console.WriteLine("Message from FurtherDerivedClass.");
//     }
// }

```
Key Points:
A sealed method must override a method from a base class.

Once sealed, the method cannot be overridden in further derived classes.

This can be used to enforce behavior consistency and enhance security in your application design.

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

# Extension Methods in C#

An **extension method** in C# allows you to add new methods to an existing type without modifying the original type or creating a derived type. This is particularly useful when you want to add functionality to classes that you don't own or can't change, like built-in .NET classes.

## How to Create an Extension Method

1. **Static Class:** Define a static class to contain the extension method.
2. **Static Method:** The method itself must also be `static`.
3. **`this` Keyword:** Add the `this` modifier to the first parameter of the method. The `this` keyword specifies which type the method will extend.

### Syntax
```csharp
public static class MyExtensions
{
    public static ReturnType MethodName(this TargetType target, params)
    {
        // Method logic here
    }
}
```
Example: Extension Method for string

Let's add an extension method to the string class to check if a string contains only digits.

```c#
using System;

public static class StringExtensions
{
    public static bool IsNumeric(this string input)
    {
        foreach (char c in input)
        {
            if (!char.IsDigit(c))
            {
                return false;
            }
        }
        return true;
    }
}

class Program
{
    static void Main()
    {
        string test = "12345";
        Console.WriteLine(test.IsNumeric()); // Output: True

        string test2 = "12a45";
        Console.WriteLine(test2.IsNumeric()); // Output: False
    }
}

```

Key Points About Extension Methods
Static Class: Extension methods must be defined in a static class.

Namespaces: To use an extension method, the namespace where it is defined must be imported with a using directive.

Enhancing Readability: They allow you to call the method as if it were a member of the original type.

Non-invasive: Extension methods do not actually modify the original type.

Real-World Use Case
```c#
using System;

public static class DateTimeExtensions
{
    public static int Age(this DateTime birthDate)
    {
        var today = DateTime.Today;
        int age = today.Year - birthDate.Year;
        if (birthDate.Date > today.AddYears(-age)) age--;
        return age;
    }
}

class Program
{
    static void Main()
    {
        DateTime birthDate = new DateTime(1990, 4, 24);
        Console.WriteLine($"Age: {birthDate.Age()}"); // Example Output: Age: 35
    }
}

```

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
