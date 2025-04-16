# Object-Oriented Programming (OOP) in C# – Akshay Yeole

Welcome to the **Object-Oriented Programming (OOP) in C#** repository by **Akshay Yeole**.  
This repository is a beginner-friendly reference for understanding key OOP principles in C#, such as:

- Encapsulation
- Inheritance
- Polymorphism
- Abstraction

---

## 🔒 Encapsulation

**Encapsulation** is one of the four fundamental OOP principles.  
It is the process of wrapping data (fields) and methods that operate on that data into a single unit, typically a class.

### 🔹 Why Use Encapsulation?

- Protects data from unauthorized access.
- Helps in maintaining the integrity of the object state.
- Allows validation before updating fields.
- Promotes modularity and code maintenance.

---

### 💻 Example in C#

Here's a simple example demonstrating encapsulation using a `BankAccount` class:

```csharp
public class BankAccount
{
    private decimal balance; // Encapsulated field

    // Public getter method to access balance
    public decimal GetBalance()
    {
        return balance;
    }

    // Public setter method to modify balance safely
    public void Deposit(decimal amount)
    {
        if (amount > 0)
        {
            balance += amount;
        }
    }
}
```

# 🧊 Abstraction in C#

Abstraction in C# is a fundamental concept in object-oriented programming (OOP) that focuses on **hiding the implementation details** of a class while exposing only the **essential features**. This approach simplifies complex systems and enhances code maintainability.

---

## 🔹 Key Points About Abstraction in C#

- Exposes only relevant details to the user.
- Hides background implementation and internal behavior.
- Enhances **security**, **modularity**, and **flexibility**.
- Achieved using **abstract classes** and **interfaces**.

---

## 📂 More OOP Concepts Coming Soon!

Stay tuned as we dive deeper into C# OOP concepts. Upcoming sections will include:

### 🧬 Inheritance
Reusing existing code through class hierarchies.

### 🎭 Polymorphism
Using the same interface for different data types or classes.

Each section will include:
- ✅ Clear explanations  
- 💡 Real-world examples  
- 🧑‍💻 Best practices

To strengthen your understanding and skillset in C# OOP.

---

## 📧 Contact

Have feedback or want to collaborate?

- 📫 Email: [akshay-yeole@outlook.com](akshay-yeole@outlook.com)
- 💼 LinkedIn: [Akshay Yeole](https://www.linkedin.com/in/akshayyeole) 

Feel free to open an issue or submit a pull request if you'd like to contribute or suggest improvements.

---

## ⭐️ Star This Repo

If you find this project helpful or informative:

- Please **star ⭐️ this repository** to show your support.
- Share it with your peers or fellow developers who are learning **C#** and **OOP**.

Your support motivates continued updates and improvements to this educational resource!

---

> Made with 💻 by Akshay

