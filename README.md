# Problem Solving in C# — From Absolute Beginner to Application Builder

> A complete, progressive, practical course for learning how to solve problems and turn solutions into reliable C# applications.

This guide starts with **zero assumed programming knowledge**. It explains the ideas first, then the C# syntax, then the algorithms, and finally a complete application built one small step at a time.

The main project is a command-line **Task Manager** that can create, list, update, delete, search, and persist tasks in a JSON file. It is deliberately small enough to understand, but rich enough to teach real problem-solving and application-building habits.

---

## Table of Contents

1. [How to Use This Guide](#1-how-to-use-this-guide)
2. [Chapter 1 — What Problem Solving Means](#2-chapter-1--what-problem-solving-means)
3. [Chapter 2 — A Short History](#3-chapter-2--a-short-history)
4. [Chapter 3 — Why C# and .NET](#4-chapter-3--why-c-and-net)
5. [Chapter 4 — Install and Run Your First Program](#5-chapter-4--install-and-run-your-first-program)
6. [Chapter 5 — The Problem-Solving Process](#6-chapter-5--the-problem-solving-process)
7. [Chapter 6 — Variables, Types, and Expressions](#7-chapter-6--variables-types-and-expressions)
8. [Chapter 7 — Input, Output, and Validation](#8-chapter-7--input-output-and-validation)
9. [Chapter 8 — Decisions and Repetition](#9-chapter-8--decisions-and-repetition)
10. [Chapter 9 — Methods and Decomposition](#10-chapter-9--methods-and-decomposition)
11. [Chapter 10 — Collections and Algorithms](#11-chapter-10--collections-and-algorithms)
12. [Chapter 11 — Complexity and Choosing an Algorithm](#12-chapter-11--complexity-and-choosing-an-algorithm)
13. [Chapter 12 — Debugging and Testing](#13-chapter-12--debugging-and-testing)
14. [Chapter 13 — Object-Oriented Problem Solving](#14-chapter-13--object-oriented-problem-solving)
15. [Chapter 14 — Files, JSON, Exceptions, and Configuration](#15-chapter-14--files-json-exceptions-and-configuration)
16. [Chapter 15 — Build the Task Manager: Foundation](#16-chapter-15--build-the-task-manager-foundation)
17. [Chapter 16 — Build the Task Manager: Features](#17-chapter-16--build-the-task-manager-features)
18. [Chapter 17 — Build the Task Manager: Architecture and Quality](#18-chapter-17--build-the-task-manager-architecture-and-quality)
19. [Chapter 18 — Advanced Problem-Solving Techniques](#19-chapter-18--advanced-problem-solving-techniques)
20. [Chapter 19 — From Console Program to Production Application](#20-chapter-19--from-console-program-to-production-application)
21. [Chapter 20 — Mastery Roadmap and Challenges](#21-chapter-20--mastery-roadmap-and-challenges)
22. [Appendix A — C# Vocabulary](#appendix-a--c-vocabulary)
23. [Appendix B — Problem-Solving Checklist](#appendix-b--problem-solving-checklist)

---

## 1. How to Use This Guide

### 1.1 The learning loop

For every chapter, follow this loop:

1. **Read the idea.** Do not rush to code.
2. **Predict the result.** Before running a program, write down what you think it will do.
3. **Type the code yourself.** Avoid copying until you have tried.
4. **Run the code.** A compiler error is feedback, not failure.
5. **Change one thing.** Experiment with a value, condition, or method.
6. **Explain it aloud.** If you cannot explain a line, you do not yet own it.
7. **Solve the exercises without looking at the answer.**

### 1.2 What “mastery” means here

Mastery does not mean memorizing every C# feature. It means that you can:

- understand an unfamiliar problem;
- ask precise questions about inputs, outputs, and rules;
- split a large problem into smaller problems;
- choose an appropriate data structure and algorithm;
- write clear C# code;
- test normal, boundary, and invalid cases;
- debug systematically;
- explain your design choices;
- improve a solution without breaking its behavior;
- build and maintain an application.

### 1.3 Recommended tools

Use one of these setups:

- **.NET SDK** plus Visual Studio, Visual Studio Code, or JetBrains Rider;
- a terminal for `dotnet` commands;
- Git for saving versions of your work.

The examples use modern C# and a standard .NET console project. The concepts also apply to web, desktop, mobile, games, cloud, and data applications.

---

# 2. Chapter 1 — What Problem Solving Means

## 2.1 The word “problem”

A **problem** is a situation in which you want a result but the path to that result is not immediately known.

Examples:

- Find the largest number in a list.
- Decide whether a password is valid.
- Calculate the total price of a shopping basket.
- Store tasks so that they are still present tomorrow.
- Find the shortest route between two locations.

A programming problem is not simply “write code.” It is a question that can be answered by following precise instructions.

## 2.2 The four parts of a programming problem

Before writing code, identify:

| Part | Question | Example: task manager |
|---|---|---|
| Input | What information enters the program? | Task title, description, due date |
| Output | What result should the program produce? | A saved task or a task list |
| Rules | What must always be true? | A title cannot be empty |
| Constraints | What limits exist? | The file may not exist or may be invalid |

A fifth part is often useful:

| Part | Question |
|---|---|
| Success measure | How do we know the solution is correct? | The task appears after restarting the program |

## 2.3 Algorithm, program, and application

These words are related but different:

- An **algorithm** is a finite sequence of steps for solving a problem.
- A **program** is an algorithm expressed in a programming language.
- An **application** is a program organized to provide useful behavior to a user or another system.

Example algorithm for finding the largest number:

1. Start with the first number as the current largest.
2. Look at each remaining number.
3. If the current number is larger, replace the current largest.
4. Return the current largest.

C# is the language used to express this algorithm.

## 2.4 Syntax and semantics

Two important words:

- **Syntax** means the grammar of the language: what arrangement of symbols is legal.
- **Semantics** means the meaning of legal code: what the code does.

This is syntactically valid:

```csharp
int age = 20;
```

It declares an integer variable named `age` and gives it the value `20`.

This is syntactically invalid:

```csharp
int = age 20;
```

The symbols are not arranged according to C# grammar.

This is syntactically valid but may be logically wrong:

```csharp
int yearsUntilRetirement = 20 - age;
```

If `age` is 40, the result is `-20`; the compiler cannot know whether that is a mistake in your business rule.

## 2.5 The most important habit: separate understanding from implementation

Do not start with:

> “Which C# keyword should I use?”

Start with:

> “What exactly must happen?”

Then write the solution in plain language, called **pseudocode**:

```text
ask the user for a task title
if the title is empty
    show an error
otherwise
    create a task
    save the task
    show a success message
```

Only after the steps are clear should you translate them into C#.

## 2.6 Exercises

1. Describe the inputs, outputs, rules, and constraints for a calculator.
2. Write pseudocode for checking whether a number is even.
3. Write pseudocode for finding the smallest number in a list.
4. Describe a real-world process that could be represented as an algorithm.

---

# 3. Chapter 2 — A Short History

Problem solving is older than computers. Humans have always created procedures for counting, measuring, organizing, and predicting.

## 3.1 Early algorithms

Ancient mathematical works included repeatable procedures. Euclid's algorithm, described in ancient Greek mathematics, finds the greatest common divisor of two numbers by repeatedly using remainders.

Centuries later, the name **algorithm** became associated with the Persian mathematician Muhammad ibn Musa al-Khwarizmi. His mathematical procedures helped establish the idea that a calculation can be described as a sequence of mechanical steps.

## 3.2 Mechanical calculation and formal logic

Mechanical calculators showed that repeated arithmetic could be automated. In the nineteenth century, Charles Babbage designed general-purpose mechanical computing machines, and Ada Lovelace described how a machine could follow a sequence of operations beyond simple arithmetic.

In the twentieth century, formal logic and theoretical computer science asked a deeper question:

> Which problems can be solved by a mechanical procedure at all?

Ideas from Alan Turing, Alonzo Church, and others gave computer science mathematical models of computation.

## 3.3 From machine instructions to high-level languages

Early programmers had to work close to hardware. Over time, higher-level languages allowed humans to express ideas more naturally:

1. machine code;
2. assembly language;
3. procedural languages;
4. object-oriented languages;
5. managed runtime languages;
6. modern multi-paradigm languages.

Each level hides some details so that the programmer can focus on the problem.

## 3.4 The history of C#

C# was created at Microsoft and first released in the early 2000s as part of the .NET ecosystem. It was designed as a modern, strongly typed, object-oriented language with influences from languages such as C, C++, Java, and others.

C# later became open source and cross-platform through the evolution of .NET. Today, C# can be used for:

- web applications and APIs;
- desktop applications;
- cloud services;
- games;
- mobile applications;
- automation tools;
- data processing;
- command-line programs;
- libraries and developer tools.

The historical lesson is important: languages change, but the core skill remains **turning a vague goal into precise steps**.

---

# 4. Chapter 3 — Why C# and .NET

## 4.1 C# is a language; .NET is a platform

It is useful to distinguish:

- **C#**: the language in which you write source code.
- **.NET**: the platform that provides the runtime, libraries, tools, and project system.
- **CLR**: the Common Language Runtime, which executes managed .NET code.
- **SDK**: the Software Development Kit, including compilers and command-line tools.

A simplified pipeline is:

```text
C# source code
        ↓
C# compiler
        ↓
Intermediate Language (IL)
        ↓
.NET runtime and JIT compiler
        ↓
Machine instructions
        ↓
Program result
```

## 4.2 Why use C# for problem solving?

C# is useful for learning problem solving because it provides:

- readable syntax;
- strong type checking;
- excellent standard libraries;
- powerful collections;
- object-oriented and functional features;
- async programming support;
- mature tooling and debugging;
- a large ecosystem;
- portability across operating systems.

## 4.3 What C# does not do for you

C# cannot decide your requirements. It cannot automatically know:

- whether an empty title should be allowed;
- whether dates are local or UTC;
- whether duplicate tasks are legal;
- what “high priority” means;
- which algorithm is appropriate;
- whether a user input is trustworthy.

The language gives you tools. **You provide the reasoning.**

---

# 5. Chapter 4 — Install and Run Your First Program

## 5.1 Check whether .NET is installed

Open a terminal and run:

```bash
dotnet --version
```

Meaning of each part:

- `dotnet` is the command-line driver for .NET.
- `--version` asks the driver to print the installed SDK version.

If the command is not found, install the current .NET SDK from the official .NET website, then open a new terminal.

## 5.2 Create a console project

Run:

```bash
dotnet new console -n ProblemSolvingJourney
cd ProblemSolvingJourney
dotnet run
```

Line by line:

- `dotnet` selects the .NET command-line tool.
- `new` tells it to create something from a template.
- `console` selects a console application template.
- `-n` means “name.”
- `ProblemSolvingJourney` is the project name.
- `cd` means “change directory.”
- `dotnet run` builds the project and runs the result.

## 5.3 The first program

Replace the generated code with:

```csharp
using System;

Console.WriteLine("Hello, problem solver!");
```

Explanation:

| Code | Meaning |
|---|---|
| `using` | Makes names from a namespace available without writing their full name. |
| `System` | A standard .NET namespace containing common types and features. |
| `;` | Ends a C# statement. |
| `Console` | A .NET class for interacting with the terminal. |
| `.` | Accesses a member of a type or object. |
| `WriteLine` | Writes text and then moves to a new line. |
| `(` and `)` | Hold the arguments passed to a method. |
| `"Hello..."` | A string literal. |

The complete execution is:

1. The program starts.
2. It calls `Console.WriteLine`.
3. The string is sent to the console.
4. The program ends.

## 5.4 Comments

Comments explain code to humans and are ignored by the compiler:

```csharp
// This is a single-line comment.
Console.WriteLine("The program is running.");

/*
   This is a multi-line comment.
*/
```

Do not comment every obvious line. Prefer comments that explain **why**, not merely **what**.

## 5.5 First modification exercise

Change the program to print:

- your name;
- your current learning goal;
- one reason you want to learn problem solving.

Use three `Console.WriteLine` calls. Then run the program again.

---

# 6. Chapter 5 — The Problem-Solving Process

Use this repeatable process for almost every programming problem.

## Step 1: Restate the problem

Turn a vague request into one precise sentence.

Vague:

> “Make a task app.”

Precise first version:

> “Allow a user to create a task with a non-empty title and display all saved tasks.”

## Step 2: Identify examples

Examples expose missing rules:

| Input | Expected result |
|---|---|
| `Buy milk` | A task is created |
| empty title | An error is displayed |
| three saved tasks | All three are listed |
| no saved tasks | A helpful empty-state message |

## Step 3: Identify edge cases

An **edge case** is an unusual but valid or potentially dangerous situation:

- empty input;
- whitespace-only input;
- negative number;
- zero items;
- one item;
- a very large value;
- duplicate values;
- missing file;
- malformed file;
- unexpected user choice.

## Step 4: Write pseudocode

```text
load tasks from storage
repeat until the user chooses Exit
    show menu
    read choice
    if choice is Add
        read and validate task information
        add task
        save tasks
    else if choice is List
        display tasks
    else if choice is Exit
        stop
    else
        show an unknown-choice message
```

## Step 5: Choose data and operations

Ask:

- Is the data one value or many values?
- Do I need order?
- Do I need fast lookup by key?
- Can items be changed?
- Should invalid states be impossible?

## Step 6: Implement the smallest working version

Do not build search, cloud synchronization, notifications, and analytics before the basic add-and-list flow works.

## Step 7: Test and improve

Run normal cases, edge cases, and invalid cases. Then refactor only when you understand the current behavior.

---

# 7. Chapter 6 — Variables, Types, and Expressions

## 7.1 A variable is a named storage location

```csharp
int age = 25;
```

Word by word:

- `int` is the type: a whole number.
- `age` is the variable name.
- `=` assigns the value on the right to the variable on the left.
- `25` is an integer literal.
- `;` ends the statement.

You can later change the value:

```csharp
age = 26;
```

## 7.2 Common built-in types

| Type | Example | Use |
|---|---|---|
| `int` | `42` | Whole numbers |
| `long` | `9000000000L` | Larger whole numbers |
| `double` | `3.14` | General decimal calculations |
| `decimal` | `19.99m` | Financial values |
| `bool` | `true` | True or false |
| `char` | `'A'` | One character |
| `string` | `"hello"` | Text |
| `DateTime` | `DateTime.UtcNow` | Date and time |
| `DateTime?` | `null` or a date | Optional date and time |

## 7.3 Value and reference concepts

A value type generally stores its value directly. A reference type variable refers to an object.

```csharp
int firstNumber = 10;
int secondNumber = firstNumber;
secondNumber = 20;
```

`firstNumber` remains `10`.

For a class object:

```csharp
Person firstPerson = new Person();
Person secondPerson = firstPerson;
```

Both variables refer to the same object unless a separate object is created.

## 7.4 Operators

```csharp
int total = 10 + 5;
int difference = 10 - 5;
int product = 10 * 5;
int quotient = 10 / 5;
int remainder = 10 % 3;
```

Comparison operators produce `bool` values:

```csharp
bool isAdult = age >= 18;
bool same = firstNumber == secondNumber;
bool different = firstNumber != secondNumber;
```

Logical operators combine conditions:

```csharp
bool canEnter = isAdult && hasTicket;
bool needsHelp = isMinor || hasAccessibilityNeed;
bool isNotEmpty = !string.IsNullOrWhiteSpace(text);
```

- `&&` means AND: both conditions must be true.
- `||` means OR: at least one condition must be true.
- `!` means NOT: reverses true and false.

## 7.5 Strings and interpolation

```csharp
string name = "Maya";
int score = 95;
string message = $"{name} scored {score} points.";
```

- `$` enables string interpolation.
- `{name}` inserts the variable's value.
- `{score}` inserts the integer as text.

Useful string operations:

```csharp
string cleaned = input.Trim();
string lower = input.ToLowerInvariant();
bool startsWithA = input.StartsWith("A", StringComparison.OrdinalIgnoreCase);
```

## 7.6 Nullable values

A nullable value can contain a normal value or `null`:

```csharp
DateTime? dueDate = null;
```

Check it safely:

```csharp
if (dueDate.HasValue)
{
    Console.WriteLine(dueDate.Value.ToShortDateString());
}
```

Or use pattern matching:

```csharp
if (dueDate is DateTime date)
{
    Console.WriteLine(date.ToShortDateString());
}
```

## 7.7 Exercises

1. Calculate the area of a rectangle.
2. Convert Celsius to Fahrenheit.
3. Decide whether a number is positive, negative, or zero.
4. Build a full name using string interpolation.
5. Explain why money is usually represented with `decimal` rather than `double`.

---

# 8. Chapter 7 — Input, Output, and Validation

## 8.1 Read text from the console

```csharp
Console.Write("Enter your name: ");
string? name = Console.ReadLine();
Console.WriteLine($"Hello, {name}!");
```

`Console.ReadLine()` may return `null`, so `string?` communicates that possibility to the compiler and to the reader.

## 8.2 Never trust input

Users can enter:

- nothing;
- spaces;
- letters where a number is expected;
- numbers outside the allowed range;
- unexpected commands.

Validation is the process of checking whether input satisfies the rules.

```csharp
Console.Write("Enter your age: ");
string? text = Console.ReadLine();

if (int.TryParse(text, out int age) && age >= 0 && age <= 130)
{
    Console.WriteLine($"Your age is {age}.");
}
else
{
    Console.WriteLine("Please enter an age from 0 to 130.");
}
```

Why `TryParse` is useful:

- it attempts conversion;
- it returns `true` when conversion succeeds;
- it returns `false` instead of throwing an exception for normal invalid input;
- it places the converted result in `age`.

## 8.3 A reusable required-text method

```csharp
static string ReadRequiredText(string prompt)
{
    while (true)
    {
        Console.Write(prompt);
        string value = Console.ReadLine()?.Trim() ?? "";

        if (!string.IsNullOrWhiteSpace(value))
        {
            return value;
        }

        Console.WriteLine("A value is required.");
    }
}
```

Line by line:

1. `static` means the method belongs to the class rather than a particular object.
2. `string` is the return type.
3. `ReadRequiredText` is the method name.
4. `string prompt` is a parameter containing the message to display.
5. `while (true)` creates a loop that continues until a `return` is reached.
6. `Console.Write(prompt)` displays the prompt without a new line.
7. `Console.ReadLine()` reads user input.
8. `?.Trim()` trims whitespace only if the input is not null.
9. `?? ""` uses an empty string if the input is null.
10. `IsNullOrWhiteSpace` rejects empty and whitespace-only input.
11. `return value` sends the valid text back to the caller.

---

# 9. Chapter 8 — Decisions and Repetition

## 9.1 `if` statements

```csharp
if (temperature > 30)
{
    Console.WriteLine("It is hot.");
}
else if (temperature < 10)
{
    Console.WriteLine("It is cold.");
}
else
{
    Console.WriteLine("The temperature is moderate.");
}
```

The condition inside parentheses must produce a `bool` value.

## 9.2 `switch` statements

Use `switch` when one value can have several known alternatives:

```csharp
switch (choice)
{
    case "1":
        Console.WriteLine("Add selected.");
        break;
    case "2":
        Console.WriteLine("List selected.");
        break;
    case "0":
        Console.WriteLine("Goodbye.");
        break;
    default:
        Console.WriteLine("Unknown choice.");
        break;
}
```

- `case` describes one matching value.
- `break` leaves the switch.
- `default` handles all other values.

## 9.3 `while` loops

```csharp
int count = 1;
while (count <= 3)
{
    Console.WriteLine(count);
    count++;
}
```

`count++` increases the value by one. Always ensure the loop can eventually stop.

## 9.4 `for` loops

```csharp
for (int index = 0; index < 5; index++)
{
    Console.WriteLine(index);
}
```

The three parts are:

1. initialization: `int index = 0`;
2. condition: `index < 5`;
3. update: `index++`.

## 9.5 `foreach` loops

Use `foreach` to visit each item in a collection:

```csharp
string[] names = { "Ari", "Bo", "Cy" };

foreach (string name in names)
{
    Console.WriteLine(name);
}
```

## 9.6 Loop-control keywords

- `break` stops the loop immediately.
- `continue` skips the rest of the current iteration and begins the next one.

Use them intentionally. Excessive early exits can make control flow difficult to understand.

---

# 10. Chapter 9 — Methods and Decomposition

## 10.1 Why methods matter

A long procedure is hard to understand and test. A method gives one part of the solution a name.

```csharp
static int Add(int left, int right)
{
    return left + right;
}
```

- `static`: callable without creating an object of the containing class.
- `int`: the method returns an integer.
- `Add`: the method name.
- `(int left, int right)`: two parameters.
- `return`: sends a result to the caller.

Use it:

```csharp
int result = Add(2, 3);
```

## 10.2 `void` methods

A method that does not return a value uses `void`:

```csharp
static void ShowWelcome()
{
    Console.WriteLine("Welcome!");
}
```

## 10.3 Method design rules

A good method usually:

- has one clear responsibility;
- has a meaningful name;
- accepts the data it needs as parameters;
- returns a useful result or performs one clear action;
- does not secretly change unrelated state.

Bad name:

```csharp
DoIt();
```

Better names:

```csharp
ValidateTaskTitle();
CalculateTotal();
DisplayTaskList();
```

## 10.4 Scope

A variable declared inside a method normally exists only within that method:

```csharp
static void Example()
{
    int localValue = 10;
    Console.WriteLine(localValue);
}
```

Trying to use `localValue` outside `Example` causes a compiler error.

## 10.5 Guard clauses

A guard clause handles invalid conditions early:

```csharp
static decimal CalculateDiscount(decimal price, decimal percentage)
{
    if (price < 0)
    {
        throw new ArgumentOutOfRangeException(nameof(price));
    }

    if (percentage < 0 || percentage > 100)
    {
        throw new ArgumentOutOfRangeException(nameof(percentage));
    }

    return price * percentage / 100m;
}
```

This keeps the main calculation easy to read.

---

# 11. Chapter 10 — Collections and Algorithms

## 11.1 Arrays

An array has a fixed length:

```csharp
int[] scores = { 90, 75, 88 };
Console.WriteLine(scores[0]);
```

Indexes start at zero. `scores[0]` is the first element.

## 11.2 Lists

A `List<T>` grows and shrinks:

```csharp
List<string> names = new List<string>();
names.Add("Ari");
names.Add("Bo");
names.Remove("Ari");
```

`T` is a placeholder for the element type. `List<string>` means a list of strings.

## 11.3 Dictionaries

A dictionary stores key-value pairs:

```csharp
Dictionary<int, string> namesById = new();
namesById[10] = "Ari";
Console.WriteLine(namesById[10]);
```

Use a dictionary when looking up a value by a key is central to the problem.

## 11.4 Sets

A `HashSet<T>` stores unique values:

```csharp
HashSet<string> tags = new();
tags.Add("work");
tags.Add("work");
Console.WriteLine(tags.Count); // 1
```

## 11.5 A linear search algorithm

```csharp
static int FindIndex(int[] numbers, int target)
{
    for (int index = 0; index < numbers.Length; index++)
    {
        if (numbers[index] == target)
        {
            return index;
        }
    }

    return -1;
}
```

The algorithm checks each item from left to right. Returning `-1` communicates “not found.”

## 11.6 Sorting and LINQ

LINQ provides expressive operations over collections:

```csharp
using System.Linq;

List<int> numbers = new() { 5, 1, 4, 2 };
List<int> sorted = numbers.OrderBy(number => number).ToList();
List<int> even = numbers.Where(number => number % 2 == 0).ToList();
```

The expression `number => number % 2 == 0` is a lambda:

- `number` is the input parameter;
- `=>` separates the parameter from the expression;
- `number % 2 == 0` is the result condition.

## 11.7 Common collection choices

| Need | Good starting choice |
|---|---|
| Fixed sequence | Array |
| Growing ordered sequence | `List<T>` |
| Lookup by key | `Dictionary<TKey, TValue>` |
| Unique membership | `HashSet<T>` |
| First-in-first-out work | `Queue<T>` |
| Last-in-first-out work | `Stack<T>` |
| Read-only public result | `IReadOnlyList<T>` |

---

# 12. Chapter 11 — Complexity and Choosing an Algorithm

## 12.1 Why performance matters

A solution can be correct for ten items and unusable for ten million items. Complexity describes how resource usage grows as input grows.

## 12.2 Big O notation

Common categories:

| Complexity | Informal meaning | Example |
|---|---|---|
| `O(1)` | Constant time | Access an array element by index |
| `O(log n)` | Grows slowly | Binary search in sorted data |
| `O(n)` | Grows with input size | Linear search |
| `O(n log n)` | Efficient general sorting | Typical comparison sorting |
| `O(n²)` | Every item compared with many others | Nested-loop pair comparison |

## 12.3 Binary search

Binary search requires sorted data:

```csharp
static int BinarySearch(int[] numbers, int target)
{
    int low = 0;
    int high = numbers.Length - 1;

    while (low <= high)
    {
        int middle = low + (high - low) / 2;

        if (numbers[middle] == target)
        {
            return middle;
        }

        if (numbers[middle] < target)
        {
            low = middle + 1;
        }
        else
        {
            high = middle - 1;
        }
    }

    return -1;
}
```

Reasoning:

1. Inspect the middle item.
2. If it is the target, stop.
3. If the target is larger, discard the lower half.
4. Otherwise, discard the upper half.
5. Repeat until the search area is empty.

## 12.4 Choosing an algorithm

Ask:

1. Is the data already sorted?
2. How large can the input become?
3. Is memory limited?
4. Is the answer needed once or repeatedly?
5. Can preprocessing make repeated work cheaper?
6. Is correctness or speed the primary concern?

Do not choose a complicated algorithm merely because it is theoretically faster. First create a correct baseline, then measure.

---

# 13. Chapter 12 — Debugging and Testing

## 13.1 Three kinds of errors

### Compile-time errors

The compiler cannot understand or type-check the program.

```csharp
int age = "twenty";
```

### Runtime errors

The program starts but fails during execution, such as reading a missing file without handling the situation.

### Logic errors

The program runs but produces the wrong result. These are often the most important errors because the computer believes the instructions are valid.

## 13.2 A debugging procedure

1. Reproduce the problem reliably.
2. Record the exact input.
3. State the expected result.
4. State the actual result.
5. Find the smallest failing example.
6. Inspect values at important points.
7. Form one hypothesis.
8. Make one change.
9. Run the same test again.
10. Add a regression test so the bug does not return.

## 13.3 Breakpoints and stepping

In an IDE, place a breakpoint on a line. When execution pauses, inspect:

- local variables;
- method parameters;
- the call stack;
- the next line to execute.

Stepping modes:

- **Step over**: execute the current line without entering called methods.
- **Step into**: enter the called method.
- **Step out**: finish the current method and return to its caller.

## 13.4 Assertions

An assertion states something that should be true:

```csharp
if (total < 0)
{
    throw new InvalidOperationException("Total cannot be negative.");
}
```

## 13.5 Unit testing idea

A unit test follows Arrange–Act–Assert:

```text
Arrange: create the input
Act: call the method
Assert: compare the result with the expected result
```

Example with xUnit-style syntax:

```csharp
[Fact]
public void Add_ReturnsTheSum()
{
    // Arrange
    int left = 2;
    int right = 3;

    // Act
    int result = Calculator.Add(left, right);

    // Assert
    Assert.Equal(5, result);
}
```

Test at least:

- normal cases;
- empty cases;
- minimum and maximum values;
- invalid input;
- duplicate data;
- persistence failures;
- behavior after a previous operation.

---

# 14. Chapter 13 — Object-Oriented Problem Solving

Object-oriented programming is one way to organize a solution around data and behavior.

## 14.1 Class and object

A **class** is a blueprint. An **object** is an instance created from that blueprint.

```csharp
public class Counter
{
    public int Value { get; private set; }

    public void Increase()
    {
        Value++;
    }
}
```

Create an object:

```csharp
Counter counter = new Counter();
counter.Increase();
Console.WriteLine(counter.Value);
```

## 14.2 Encapsulation

Encapsulation keeps data and the rules that protect it together. `private set` means outside code can read `Value` but cannot assign it directly.

## 14.3 Abstraction

Abstraction exposes what a caller needs and hides irrelevant implementation details.

```csharp
public interface IClock
{
    DateTime UtcNow { get; }
}
```

A class can depend on `IClock` rather than directly depending on the system clock. That makes time-based behavior easier to test.

## 14.4 Inheritance and polymorphism

Inheritance models an “is a” relationship, but do not use it automatically. Composition is often simpler.

Polymorphism means code can use a common contract while different implementations behave differently:

```csharp
public interface INotifier
{
    void Notify(string message);
}
```

A console notifier and an email notifier can both implement `INotifier`.

## 14.5 Composition over excessive inheritance

Instead of making a huge class hierarchy, combine focused objects:

```text
TaskManager uses TaskRepository.
TaskManager uses TaskValidator.
TaskManager uses a clock.
```

This makes responsibilities visible and replaceable.

---

# 15. Chapter 14 — Files, JSON, Exceptions, and Configuration

## 15.1 Read and write a file

```csharp
File.WriteAllText("notes.txt", "Learn problem solving.");
string text = File.ReadAllText("notes.txt");
```

A file path is external input. It may be missing, locked, invalid, or inaccessible.

## 15.2 JSON

JSON is a text format for structured data:

```json
{
  "id": 1,
  "title": "Learn C#",
  "done": false
}
```

Serialize a C# object:

```csharp
using System.Text.Json;

var options = new JsonSerializerOptions { WriteIndented = true };
string json = JsonSerializer.Serialize(task, options);
```

Deserialize JSON:

```csharp
TaskItem? task = JsonSerializer.Deserialize<TaskItem>(json);
```

## 15.3 Exceptions

Exceptions represent exceptional failures. Handle failures where you can make a useful decision.

```csharp
try
{
    string text = File.ReadAllText("tasks.json");
}
catch (FileNotFoundException)
{
    Console.WriteLine("No saved file exists yet. Starting empty.");
}
catch (IOException error)
{
    Console.WriteLine($"Could not read the file: {error.Message}");
}
```

Do not use exceptions as the normal way to validate ordinary user input when `TryParse` or a direct condition is enough.

## 15.4 Date and time

Prefer UTC for stored timestamps:

```csharp
DateTime createdAt = DateTime.UtcNow;
```

A due date entered by a user may represent local calendar time. Document the choice instead of silently mixing local time and UTC.

---

# 16. Chapter 15 — Build the Task Manager: Foundation

We now build a complete application. Each file has one clear responsibility.

## 16.1 Create the project

```bash
dotnet new console -n TaskMaster
cd TaskMaster
mkdir Models Services
```

Run the empty project once:

```bash
dotnet run
```

Create this structure:

```text
TaskMaster/
├── Models/
│   ├── TaskItem.cs
│   └── TaskStatus.cs
├── Services/
│   ├── InputReader.cs
│   ├── TaskManager.cs
│   └── TaskRepository.cs
└── Program.cs
```

## 16.2 Create the task status enum

Create `Models/TaskStatus.cs`:

```csharp
namespace TaskMaster.Models;

public enum TaskStatus
{
    Todo,
    InProgress,
    Done
}
```

Line by line:

- `namespace TaskMaster.Models;` places the type in a named group.
- `public` makes the enum available to other parts of the project.
- `enum` declares a fixed set of named values.
- `TaskStatus` is the enum name.
- `Todo`, `InProgress`, and `Done` are the allowed states.

## 16.3 Create the task model

Create `Models/TaskItem.cs`:

```csharp
namespace TaskMaster.Models;

public sealed class TaskItem
{
    public int Id { get; set; }

    public string Title { get; set; } = string.Empty;

    public string Description { get; set; } = string.Empty;

    public TaskStatus Status { get; set; } = TaskStatus.Todo;

    public DateTime CreatedAt { get; set; } = DateTime.UtcNow;

    public DateTime? DueDate { get; set; }
}
```

Explanation:

- `sealed` prevents another class from inheriting from `TaskItem`; this model is simple and complete by itself.
- `{ get; set; }` creates a property that can be read and changed.
- `= string.Empty` prevents a new task's text property from starting as null.
- `TaskStatus.Todo` is the default status.
- `DateTime.UtcNow` records creation time in UTC.
- `DateTime?` means the due date is optional.

## 16.4 Create the repository

Create `Services/TaskRepository.cs`:

```csharp
using System.Text.Json;
using TaskMaster.Models;

namespace TaskMaster.Services;

public sealed class TaskRepository
{
    private readonly string _filePath;
    private readonly JsonSerializerOptions _jsonOptions = new()
    {
        WriteIndented = true
    };

    public TaskRepository(string filePath)
    {
        _filePath = filePath;
    }

    public List<TaskItem> Load()
    {
        if (!File.Exists(_filePath))
        {
            return new List<TaskItem>();
        }

        try
        {
            string json = File.ReadAllText(_filePath);
            return JsonSerializer.Deserialize<List<TaskItem>>(json, _jsonOptions)
                   ?? new List<TaskItem>();
        }
        catch (JsonException)
        {
            Console.WriteLine("The task file is not valid JSON. Starting with no tasks.");
            return new List<TaskItem>();
        }
        catch (IOException error)
        {
            Console.WriteLine($"The task file could not be read: {error.Message}");
            return new List<TaskItem>();
        }
    }

    public void Save(List<TaskItem> tasks)
    {
        string json = JsonSerializer.Serialize(tasks, _jsonOptions);
        File.WriteAllText(_filePath, json);
    }
}
```

Important reasoning:

1. The repository owns file access.
2. The rest of the application does not need to know how JSON works.
3. A missing file means there are no tasks yet.
4. Invalid JSON is reported and the program starts safely with an empty list.
5. `JsonSerializerOptions` makes the saved file readable by humans.

## 16.5 Create the task manager service

Create `Services/TaskManager.cs`:

```csharp
using TaskMaster.Models;

namespace TaskMaster.Services;

public sealed class TaskManager
{
    private readonly TaskRepository _repository;
    private readonly List<TaskItem> _tasks;

    public TaskManager(TaskRepository repository)
    {
        _repository = repository;
        _tasks = _repository.Load();
    }

    public IReadOnlyList<TaskItem> GetAll()
    {
        return _tasks
            .OrderBy(task => task.Id)
            .ToList();
    }

    public TaskItem Add(string title, string description, DateTime? dueDate)
    {
        if (string.IsNullOrWhiteSpace(title))
        {
            throw new ArgumentException("A task title is required.", nameof(title));
        }

        int nextId = _tasks.Count == 0
            ? 1
            : _tasks.Max(task => task.Id) + 1;

        TaskItem task = new()
        {
            Id = nextId,
            Title = title.Trim(),
            Description = description.Trim(),
            DueDate = dueDate
        };

        _tasks.Add(task);
        _repository.Save(_tasks);
        return task;
    }

    public bool Delete(int id)
    {
        TaskItem? task = _tasks.FirstOrDefault(item => item.Id == id);

        if (task is null)
        {
            return false;
        }

        _tasks.Remove(task);
        _repository.Save(_tasks);
        return true;
    }

    public bool UpdateStatus(int id, TaskStatus status)
    {
        TaskItem? task = _tasks.FirstOrDefault(item => item.Id == id);

        if (task is null)
        {
            return false;
        }

        task.Status = status;
        _repository.Save(_tasks);
        return true;
    }

    public IReadOnlyList<TaskItem> Search(string text)
    {
        return _tasks
            .Where(task =>
                task.Title.Contains(text, StringComparison.OrdinalIgnoreCase) ||
                task.Description.Contains(text, StringComparison.OrdinalIgnoreCase))
            .OrderBy(task => task.Id)
            .ToList();
    }
}
```

Line-by-line concepts:

- `private readonly` means the service controls the reference and does not replace it after construction.
- The constructor loads the current state once.
- `IReadOnlyList<TaskItem>` prevents callers from directly changing the manager's internal list.
- `OrderBy` creates a sorted view without changing the internal storage order.
- `FirstOrDefault` returns the first matching task or `null`.
- `task is null` is a readable null check.
- The `Add` method validates before changing state.
- `Max` finds the largest existing ID.
- An object initializer sets several properties during construction.
- The repository is saved immediately after a state-changing operation.

---

# 17. Chapter 16 — Build the Task Manager: Features

## 17.1 Create the input reader

Create `Services/InputReader.cs`:

```csharp
namespace TaskMaster.Services;

public static class InputReader
{
    public static string ReadRequiredText(string prompt)
    {
        while (true)
        {
            Console.Write(prompt);
            string value = Console.ReadLine()?.Trim() ?? string.Empty;

            if (!string.IsNullOrWhiteSpace(value))
            {
                return value;
            }

            Console.WriteLine("A value is required.");
        }
    }

    public static string ReadOptionalText(string prompt)
    {
        Console.Write(prompt);
        return Console.ReadLine()?.Trim() ?? string.Empty;
    }

    public static int ReadInt(string prompt)
    {
        while (true)
        {
            Console.Write(prompt);

            if (int.TryParse(Console.ReadLine(), out int value))
            {
                return value;
            }

            Console.WriteLine("Please enter a whole number.");
        }
    }

    public static DateTime? ReadOptionalDate(string prompt)
    {
        while (true)
        {
            Console.Write(prompt);
            string text = Console.ReadLine()?.Trim() ?? string.Empty;

            if (text.Length == 0)
            {
                return null;
            }

            if (DateTime.TryParse(text, out DateTime date))
            {
                return date.Date;
            }

            Console.WriteLine("Enter a valid date or press Enter to skip.");
        }
    }
}
```

This class centralizes repeated input behavior. If the rules change, you update one place instead of copying fixes through the entire application.

## 17.2 Create the program entry point

Replace `Program.cs` with:

```csharp
using TaskMaster.Models;
using TaskMaster.Services;

namespace TaskMaster;

public static class Program
{
    public static void Main()
    {
        TaskRepository repository = new("tasks.json");
        TaskManager manager = new(repository);

        while (true)
        {
            ShowMenu();
            string choice = Console.ReadLine()?.Trim() ?? string.Empty;
            Console.WriteLine();

            switch (choice)
            {
                case "1":
                    AddTask(manager);
                    break;
                case "2":
                    ListTasks(manager.GetAll());
                    break;
                case "3":
                    SearchTasks(manager);
                    break;
                case "4":
                    ChangeStatus(manager);
                    break;
                case "5":
                    DeleteTask(manager);
                    break;
                case "0":
                    Console.WriteLine("Goodbye.");
                    return;
                default:
                    Console.WriteLine("Unknown menu choice.");
                    break;
            }

            Console.WriteLine();
        }
    }

    private static void ShowMenu()
    {
        Console.WriteLine("=== Task Master ===");
        Console.WriteLine("1. Add task");
        Console.WriteLine("2. List tasks");
        Console.WriteLine("3. Search tasks");
        Console.WriteLine("4. Change task status");
        Console.WriteLine("5. Delete task");
        Console.WriteLine("0. Exit");
        Console.Write("Choose an option: ");
    }

    private static void AddTask(TaskManager manager)
    {
        string title = InputReader.ReadRequiredText("Title: ");
        string description = InputReader.ReadOptionalText("Description: ");
        DateTime? dueDate = InputReader.ReadOptionalDate("Due date (optional): ");

        TaskItem task = manager.Add(title, description, dueDate);
        Console.WriteLine($"Task #{task.Id} created.");
    }

    private static void ListTasks(IReadOnlyList<TaskItem> tasks)
    {
        if (tasks.Count == 0)
        {
            Console.WriteLine("No tasks found.");
            return;
        }

        foreach (TaskItem task in tasks)
        {
            string due = task.DueDate?.ToString("yyyy-MM-dd") ?? "none";
            Console.WriteLine(
                $"#{task.Id} [{task.Status}] {task.Title} | Due: {due}");

            if (!string.IsNullOrWhiteSpace(task.Description))
            {
                Console.WriteLine($"    {task.Description}");
            }
        }
    }

    private static void SearchTasks(TaskManager manager)
    {
        string text = InputReader.ReadRequiredText("Search text: ");
        ListTasks(manager.Search(text));
    }

    private static void ChangeStatus(TaskManager manager)
    {
        int id = InputReader.ReadInt("Task ID: ");
        Console.WriteLine("1. Todo");
        Console.WriteLine("2. In progress");
        Console.WriteLine("3. Done");
        int statusChoice = InputReader.ReadInt("New status: ");

        TaskStatus status = statusChoice switch
        {
            1 => TaskStatus.Todo,
            2 => TaskStatus.InProgress,
            3 => TaskStatus.Done,
            _ => throw new ArgumentException("Invalid status choice.")
        };

        bool updated = manager.UpdateStatus(id, status);
        Console.WriteLine(updated ? "Status updated." : "Task not found.");
    }

    private static void DeleteTask(TaskManager manager)
    {
        int id = InputReader.ReadInt("Task ID to delete: ");
        bool deleted = manager.Delete(id);
        Console.WriteLine(deleted ? "Task deleted." : "Task not found.");
    }
}
```

## 17.3 Understand the complete flow

When the program starts:

1. `Main` creates a `TaskRepository` connected to `tasks.json`.
2. `TaskManager` loads saved tasks.
3. The loop displays the menu.
4. The user chooses an operation.
5. `Program` handles interaction.
6. `TaskManager` owns task rules and state changes.
7. `TaskRepository` owns persistence.
8. Control returns to the menu.
9. The loop ends only when the user chooses `0`.

This separation is the first step from a script toward an application.

## 17.4 Run and test it

From the project directory:

```bash
dotnet run
```

Test this exact sequence:

1. Choose `1`.
2. Enter `Learn C#` as the title.
3. Enter `Practice problem decomposition` as the description.
4. Enter a valid date or press Enter.
5. Choose `2`; verify the task appears.
6. Choose `4`; set its status to `Done`.
7. Choose `3`; search for `c#`.
8. Choose `5`; delete the task.
9. Choose `0`.
10. Run the program again and verify the deleted task is still absent.

Inspect `tasks.json`. It is the persisted state of the application.

## 17.5 Important bug in the first version

The `ChangeStatus` method throws an exception for an invalid status menu choice. That is acceptable for demonstrating exceptions, but not ideal user experience. Improve it by replacing the switch expression with a loop that repeatedly asks until the user enters `1`, `2`, or `3`.

A safer version is:

```csharp
private static TaskStatus ReadStatus()
{
    while (true)
    {
        Console.WriteLine("1. Todo");
        Console.WriteLine("2. In progress");
        Console.WriteLine("3. Done");
        int choice = InputReader.ReadInt("New status: ");

        switch (choice)
        {
            case 1:
                return TaskStatus.Todo;
            case 2:
                return TaskStatus.InProgress;
            case 3:
                return TaskStatus.Done;
            default:
                Console.WriteLine("Choose 1, 2, or 3.");
                break;
        }
    }
}
```

Then call:

```csharp
TaskStatus status = ReadStatus();
```

This is a problem-solving improvement: the program now treats expected invalid input as a normal interaction rather than an application crash.

---

# 18. Chapter 17 — Build the Task Manager: Architecture and Quality

## 18.1 Responsibilities in the application

| Component | Responsibility |
|---|---|
| `TaskItem` | Represents task data |
| `TaskStatus` | Defines allowed states |
| `InputReader` | Reads and validates console input |
| `TaskManager` | Applies task rules and changes state |
| `TaskRepository` | Reads and writes JSON |
| `Program` | Coordinates the user interface |

This is a small layered design:

```text
Console UI → Application service → Persistence
                 ↓
              Domain model
```

## 18.2 Why this design is better than one giant method

A giant method mixes:

- menu display;
- input parsing;
- validation;
- business rules;
- file access;
- formatting.

That makes changes risky. In the separated design:

- you can replace the console UI;
- you can replace JSON with a database;
- you can test task rules without simulating the keyboard;
- you can reuse the manager from a web API.

## 18.3 Add a validator

Create `Services/TaskValidator.cs`:

```csharp
namespace TaskMaster.Services;

public static class TaskValidator
{
    public static string ValidateTitle(string title)
    {
        if (string.IsNullOrWhiteSpace(title))
        {
            return "A title is required.";
        }

        if (title.Trim().Length > 120)
        {
            return "A title cannot exceed 120 characters.";
        }

        return string.Empty;
    }
}
```

Use it in `TaskManager.Add`:

```csharp
string error = TaskValidator.ValidateTitle(title);

if (error.Length > 0)
{
    throw new ArgumentException(error, nameof(title));
}
```

A production-quality UI could display the error without using an exception for ordinary interaction. The important idea is that validation has a named, reusable home.

## 18.4 Add tests conceptually

Create a separate test project later:

```bash
dotnet new xunit -n TaskMaster.Tests
dotnet add TaskMaster.Tests reference TaskMaster
```

Example test for the title rule:

```csharp
using TaskMaster.Services;
using Xunit;

namespace TaskMaster.Tests;

public class TaskValidatorTests
{
    [Fact]
    public void EmptyTitle_ReturnsAnError()
    {
        string error = TaskValidator.ValidateTitle("   ");

        Assert.Equal("A title is required.", error);
    }

    [Fact]
    public void NormalTitle_ReturnsNoError()
    {
        string error = TaskValidator.ValidateTitle("Learn C#");

        Assert.Equal(string.Empty, error);
    }
}
```

## 18.5 Refactoring safely

A safe refactoring sequence:

1. Run all tests.
2. Make one structural change.
3. Compile.
4. Run tests.
5. Inspect the diff.
6. Repeat.

Never refactor and redesign behavior simultaneously unless you have strong tests.

---

# 19. Chapter 18 — Advanced Problem-Solving Techniques

## 19.1 Divide and conquer

Split a problem into smaller independent pieces, solve each piece, and combine results.

Examples:

- merge sort;
- processing a file in sections;
- breaking the Task Manager into model, service, repository, and UI.

## 19.2 Greedy algorithms

A greedy algorithm makes the best-looking local decision at each step. It is fast and simple when the problem has the right mathematical structure, but it is not always globally optimal.

Example question: select the largest number of non-overlapping events. Choosing the event that finishes earliest is a proven greedy strategy for that particular problem.

## 19.3 Dynamic programming

Dynamic programming solves overlapping subproblems once and reuses the results.

Typical signs:

- the problem can be split into repeated subproblems;
- a solution depends on earlier solutions;
- caching previous results is useful.

## 19.4 Backtracking

Backtracking explores choices, abandons invalid partial solutions, and returns to try another choice.

Used for:

- permutations;
- combinations;
- Sudoku-like constraint problems;
- path exploration.

## 19.5 Invariants

An **invariant** is a fact that should remain true throughout an algorithm.

For the Task Manager:

- every task ID should be positive;
- every task title should be non-empty;
- every status should be one of the enum values.

For a sorting algorithm:

- after each outer iteration, a portion of the list is in its final position.

Writing invariants makes correctness easier to reason about.

## 19.6 Recursion

A recursive method calls itself on a smaller problem:

```csharp
static int Factorial(int n)
{
    if (n <= 1)
    {
        return 1;
    }

    return n * Factorial(n - 1);
}
```

Every recursive solution needs:

1. a base case;
2. progress toward the base case;
3. a correct combination of the smaller result.

## 19.7 Immutability

Immutable data cannot be changed after creation. It reduces accidental side effects and makes concurrent reasoning easier.

For example, instead of changing a task object in many places, create a new value representing the updated task. This is especially useful in functional designs and distributed systems.

## 19.8 Async and concurrency

Asynchronous programming allows a program to wait for slow operations without blocking the thread unnecessarily.

```csharp
static async Task<string> ReadFileAsync(string path)
{
    return await File.ReadAllTextAsync(path);
}
```

- `async` marks a method that can await asynchronous operations.
- `Task<string>` represents a future result of type `string`.
- `await` pauses this method until the operation completes while allowing the runtime to do other work.

Do not add async merely because it is modern. Use it when the operation is naturally asynchronous, such as file, network, or database I/O.

---

# 20. Chapter 19 — From Console Program to Production Application

The Task Manager is a learning application. A real application adds concerns gradually.

## 20.1 Web API version

A web API would expose operations such as:

```text
GET    /tasks
POST   /tasks
PUT    /tasks/{id}/status
DELETE /tasks/{id}
```

The same domain rules should remain understandable even when the user interface changes from console commands to HTTP requests.

## 20.2 Database persistence

JSON is suitable for learning and small personal tools. A database becomes useful when you need:

- concurrent users;
- reliable queries;
- transactions;
- indexes;
- relationships;
- backups;
- access control.

Before introducing a database, define the data model and invariants clearly. A database does not fix unclear requirements.

## 20.3 Dependency injection

Instead of constructing every dependency inside a class, provide dependencies from outside:

```csharp
public TaskManager(TaskRepository repository)
{
    _repository = repository;
    _tasks = repository.Load();
}
```

This constructor injection is already a basic form of dependency injection. It allows tests or future versions to provide a different repository.

## 20.4 Logging

A real application needs records of important events:

- application start;
- task creation;
- persistence failures;
- unexpected exceptions.

Logs should help diagnose a problem without exposing secrets or unnecessary personal data.

## 20.5 Security principles

Always consider:

- validate data at trust boundaries;
- do not store secrets in source code;
- use least privilege;
- avoid displaying sensitive information in logs;
- protect files and databases;
- update dependencies;
- treat external data as untrusted.

## 20.6 Deployment thinking

Before deployment, ask:

- Where will configuration come from?
- Where will data be stored?
- How will errors be observed?
- How will the application be updated?
- How will backups and recovery work?
- What happens when an external service is unavailable?

These are problem-solving questions, not merely deployment questions.

---

# 21. Chapter 20 — Mastery Roadmap and Challenges

## Level 1: Absolute beginner

Learn:

- terminal commands;
- program entry point;
- variables and types;
- operators;
- conditions;
- loops;
- methods;
- strings;
- basic input validation.

Projects:

1. greeting program;
2. temperature converter;
3. calculator;
4. number guessing game;
5. simple quiz.

## Level 2: Practical problem solver

Learn:

- arrays and lists;
- dictionaries and sets;
- search and sorting;
- file I/O;
- exceptions;
- JSON;
- debugging;
- unit testing.

Projects:

1. contact book;
2. expense tracker;
3. inventory manager;
4. text-file analyzer;
5. improved Task Master.

## Level 3: Application developer

Learn:

- classes and interfaces;
- encapsulation;
- composition;
- layered architecture;
- dependency injection;
- async programming;
- database basics;
- HTTP and APIs.

Projects:

1. REST API for tasks;
2. notes application with search;
3. library management system;
4. booking system;
5. personal finance tracker.

## Level 4: Advanced engineer

Learn:

- algorithm analysis;
- concurrency;
- caching;
- distributed systems;
- observability;
- security;
- performance profiling;
- deployment and operations.

Projects:

1. multi-user task service;
2. background job processor;
3. event-driven notification service;
4. search service;
5. production-style portfolio application.

## 21.1 Progressive Task Master challenges

Complete these in order:

1. Prevent duplicate titles.
2. Add priority: Low, Medium, High.
3. Add a `List` command that filters by status.
4. Add a `Due today` command.
5. Add task editing.
6. Add confirmation before deletion.
7. Add export to CSV.
8. Add import from CSV with validation.
9. Add unit tests for every manager operation.
10. Replace JSON with SQLite.
11. Add an ASP.NET Core API.
12. Add a web or desktop user interface.
13. Add user accounts and authorization.
14. Add logging and error reporting.
15. Measure and improve search performance.

For every challenge, write:

- the requirement;
- examples;
- edge cases;
- pseudocode;
- implementation plan;
- tests;
- a short explanation of the design trade-offs.

## 21.2 Mastery questions

You are making real progress when you can answer these without guessing:

1. What is the input and output of this method?
2. What assumptions does this code make?
3. What happens for an empty collection?
4. What happens for invalid input?
5. What is the time complexity?
6. What is the memory complexity?
7. Which class owns this rule?
8. Can this code be tested without a terminal or file system?
9. What changes if the data source becomes a database?
10. What would fail if two users performed this operation at the same time?

---

# Appendix A — C# Vocabulary

| Word | Meaning |
|---|---|
| Argument | A value supplied when calling a method |
| Array | Fixed-size sequence of values |
| Assignment | Giving a value to a variable using `=` |
| Boolean / `bool` | A true-or-false value |
| Class | A type that describes data and behavior |
| Compiler | Program that translates and checks source code |
| Constructor | Code that runs when an object is created |
| Dependency | A component another component needs |
| Enum | A fixed set of named values |
| Exception | An object representing an exceptional failure |
| Expression | Code that produces a value |
| Field | A variable stored as part of a class or struct |
| Generic | A type or method parameterized by another type |
| Interface | A contract describing available members |
| Instance | An object created from a class |
| Invariant | A condition that should remain true |
| Iteration | One repetition of a loop |
| Lambda | A short anonymous function such as `x => x * 2` |
| Method | A named block of executable behavior |
| Namespace | A naming group for related types |
| Object | A runtime instance of a type |
| Parameter | A variable declared by a method |
| Property | A member used to expose data through `get` and `set` |
| Runtime | The environment that executes a program |
| Scope | The region where a name can be used |
| Statement | An instruction that performs an action |
| Type | A definition of what kind of value something is |
| Variable | A named location used to hold a value |

## C# symbols

| Symbol | Common meaning |
|---|---|
| `;` | End of a statement |
| `{ }` | Block of code or object initializer |
| `( )` | Method parameters, arguments, or grouping |
| `[ ]` | Array/index access or attributes |
| `.` | Access a member |
| `=` | Assignment |
| `==` | Equality comparison |
| `!=` | Inequality comparison |
| `=>` | Lambda or expression-bodied member |
| `?` | Nullable type or conditional operator, depending on context |
| `??` | Use the right side when the left side is null |
| `!` | Logical NOT, or null-forgiving operator in another context |
| `<T>` | Generic type parameter |

---

# Appendix B — Problem-Solving Checklist

Before coding:

- [ ] Can I state the problem in one sentence?
- [ ] What are the inputs?
- [ ] What is the expected output?
- [ ] What rules must always be true?
- [ ] What constraints exist?
- [ ] What examples can I write?
- [ ] What edge cases might break the solution?
- [ ] Can I write pseudocode?
- [ ] Which data structure fits the operations?
- [ ] What is the simplest correct solution?

While coding:

- [ ] Are names meaningful?
- [ ] Does each method have one responsibility?
- [ ] Am I validating external input?
- [ ] Am I avoiding duplicated rules?
- [ ] Does the code compile after a small change?
- [ ] Can I explain every line I wrote?

After coding:

- [ ] Did I test normal input?
- [ ] Did I test empty input?
- [ ] Did I test boundary values?
- [ ] Did I test invalid input?
- [ ] Did I test repeated operations?
- [ ] Did I test persistence or external failures?
- [ ] Did I measure performance if the data can grow?
- [ ] Did I record what I learned?
- [ ] Can another person understand the design?

---

## Final message to the learner

Problem solving is not a talent that some people are born with and others cannot learn. It is a trainable process:

> Understand the problem → model the data → write precise steps → implement a small solution → test it → learn from failures → improve the design.

C# is the tool you use to express those steps. Your most important skill is not memorizing syntax. It is learning to think clearly enough that the syntax has a precise job.

Start with the first exercise, run every example, make deliberate mistakes, and keep a record of the problems you solve. That is how you move from zero knowledge to mastery.
