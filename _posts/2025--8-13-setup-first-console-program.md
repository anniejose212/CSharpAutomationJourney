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

- **Prompt + greet** (done): Ask for name, greet with `"Hello, <name>!"`.
- **Add age**: Ask for age and print `age + 5` safely:
  ```csharp
  Console.Write("Enter your age: ");
  string ageText = Console.ReadLine();
  if (int.TryParse(ageText, out int age))
  {
      Console.WriteLine("In 5 years you will be: " + (age + 5));
  }
  else
  {
      Console.WriteLine("That doesn't look like a valid number.");
  }
  ```
- **Sum of two numbers**: Prompt for two integers and print their sum.
- **Commit after each change**: Small, descriptive commits help your learning journal.

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

## 8) What’s next (Lesson 2 teaser)
- Variables & data types
- Converting strings to numbers (`int.Parse` vs `int.TryParse`)
- Basic arithmetic & string interpolation (`$"Hello {name}"`)
- Tiny exercises + a short quiz
