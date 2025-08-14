---
layout: default
title:  "Welcome to Csharp Automation journey"
date:   2025-08-06 12:00:00 +1000
categories: programming
---

# Lesson 1 — Key Takeaways (Setup & First Console Program)

**Date:** 13 Aug 2025  
**Author:** Annie Jose  
**Track:** C# for Selenium & General Development

---

## 1) Accomplishments
- Installed and verified **.NET 8 SDK (LTS)**.
- Created a clean workspace with a **solution** (`.sln`) and a **console project** (`.csproj`).
- Wrote a classic C# program with an explicit `Main` method (no hidden “magic”).
- Read **user input** and printed a **personalised output** using `Console`.
- Ran the app from the terminal with `dotnet run`.
- Initialised **Git**, added a `.gitignore`, and pushed to GitHub.

---

## 2) Command cheat‑sheet

### Verify .NET
```bash
dotnet --version
```

### Create workspace & solution
```bash
mkdir LearnCS && cd LearnCS
dotnet new sln -n LearnCS
```

### Create first console app & add to solution
```bash
dotnet new console -n Lesson01.HelloCSharp
dotnet sln add Lesson01.HelloCSharp
```

### Run the app
```bash
dotnet run --project Lesson01.HelloCSharp
```

---

## 3) Program structure (no shortcuts)

Key elements you used:

- `using System;` — imports the **System** namespace to access `Console`.
- `namespace Lesson01.HelloCSharp` — groups related code logically.
- `class Program` — container for your program logic.
- `static void Main(string[] args)` — **entry point**; execution starts here.
- `Console.WriteLine(...)` — print with newline.
- `Console.Write(...)` — print without newline (prompt stays on same line).
- `Console.ReadLine()` — read user input (waits for Enter).

### Final code (Lesson 1)
```csharp
using System;

namespace Lesson01.HelloCSharp
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Welcome to Lesson 1 - C# Basics!");
            Console.Write("Please enter your name: ");
            string userName = Console.ReadLine();

            Console.WriteLine("Hello, " + userName + "! Nice to meet you.");
            Console.WriteLine("Press Enter to exit...");
            Console.ReadLine();
        }
    }
}
```

---

## 4) Git basics

### One‑time identity (global)
```bash
git config --global user.name "Annie Jose"
git config --global user.email "<your_github_email>"
```

### Init, ignore, commit
```bash
git init
# .gitignore should include: bin/, obj/, .vscode/, *.user, *.rsuser, *.suo, *.log, *.tmp, *~
git add .
git commit -m "Lesson 1: Setup project and HelloCSharp program"
```

### Push to a new GitHub repo
```bash
git remote add origin https://github.com/<your-username>/LearnCS.git
git branch -M main
git push -u origin main
```

**Tip:** Be careful to **run** commands in the terminal (don’t accidentally create files named like commands).

---

## 5) Troubleshooting you encountered (and fixes)

- **CS1031 / CS1001 / CS1026 near `Main`**: Unbalanced parentheses or stray characters.  
  ✅ Ensure `static void Main(string[] args)` (no extra comma, closing `)` present).

- **Broken strings**: “Smart quotes” or extra quotes around text.  
  ✅ Use straight quotes `"` and correct concatenation: `"Hello, " + userName + "!"`.

- **No output / wrong panel**: Looking at OUTPUT/DEBUG CONSOLE instead of TERMINAL.  
  ✅ Use **View → Terminal** and run `dotnet run --project Lesson01.HelloCSharp`.

- **`scriptcs` not recognized**: VS Code guessed the wrong runner.  
  ✅ Install **C# Dev Kit** or run via terminal with `dotnet run`.

- **`dotnet` not recognized**: PATH not refreshed or SDK not installed.  
  ✅ Reopen terminal; confirm `dotnet --version`; reinstall .NET 8 if needed.

---

## 6) Practice tasks (expand your skills)

Write a program that displays this exact format:

My Name: [Your Name]
Learning Goal: [Your Goal]
Motivation Level: 100%


(Replace the text in brackets with your own values — still hardcoded for now.)

---

## 7) Mental model (how it all fits)
```
Solution (.sln)
 └── Project (.csproj)
      └── Program.cs (entry point)
            └── Main(...) — program starts here
```

- `dotnet new` → create things (solution, project).
- `dotnet sln add` → register project in solution.
- `dotnet run` → build + execute the selected project.
- `Console` → basic I/O for console apps.

---
## 8) Key Takeaways from Today

- Every C# program must have a Main method — it’s the entry point for execution.
- Console.WriteLine(...) is for printing with a newline; Console.Write(...) keeps the cursor on the same line.
- String concatenation ("Hello, " + name) and string interpolation ($"Hello, {name}") both work — interpolation is cleaner for longer text.
- Case sensitivity matters — Console and console are not the same.
- Parentheses after methods are mandatory — Console.WriteLine("text") works, Console.WriteLine = "text"; causes errors.
- Initialize variables immediately to avoid null warnings in modern C# (nullable reference types).
- Keep your using directives relevant — unused namespaces can be removed for cleaner code.
- When adding extra methods (like PrintProfile), put them inside the class but outside Main so they’re reusable.
- For now, avoid ReadLine() and Parse() if focusing on core syntax — hardcode values to reduce complexity early on.
- A clean project structure + small, descriptive Git commits will make it easier to track your learning progress.

---
## 9) What’s next (Lesson 2 teaser)
- Variables & data types
- Tiny exercises + a short quiz
