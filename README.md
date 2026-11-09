# Problem Solving in C# — The Complete Guided Journey: From Absolute Zero to Application Builder

> **A complete, progressive, deeply-explained course.** You will start with zero assumed programming knowledge, learn to *think* like a problem solver, learn the C# language one careful step at a time, and finish by building — line by line, with every line explained — a real, working application.

---

## Welcome — Read This First

Welcome to this journey. This guide was written for one specific kind of reader: **a person who wants to move from knowing nothing about programming to being able to build working applications in C# — and, more importantly, to understand *why* every line does what it does.**

Most programming tutorials teach you *syntax first*: "this is a variable, this is a loop, memorize this." Then, when you face a real problem, you freeze — because nobody taught you how to *think*. This guide deliberately reverses that order:

1. First you learn **what a problem actually is** and how to analyze one (Chapters 1 and 5).
2. Then you learn where this craft came from and what your tools really are (Chapters 2–4).
3. Then you learn the C# language **one small tool at a time**, each tool motivated by a problem it solves (Chapters 6–14).
4. Then you build a complete application — **Task Master**, a task manager with saving, searching, updating, and deleting — one layer at a time, every single line explained (Chapters 15–19).
5. Finally, you go beyond: advanced techniques, production thinking, and a concrete roadmap to mastery (Chapters 20–22).

### What this guide is

- **Zero-to-mastery**: no assumed knowledge. Every term is explained the first time it appears. If a word is unfamiliar, check **Appendix A — C# Vocabulary**.
- **Step by step**: every chapter builds on the previous ones. Nothing is used before it has been taught.
- **Line by line**: every significant code line is explained. For the most important lines, every *word* of the line is explained.
- **Practical**: you will type real code, run it, break it, fix it, and test it.
- **Honest**: where code can fail, we show how it fails and what to do about it.

### What you will build

The capstone project of this guide is **Task Master**, a command-line task manager. By the end you will have built, with your own hands, an application that can:

| Capability | What it means |
|---|---|
| **Create** tasks | with a required title, optional description, and optional due date |
| **List** tasks | sorted by ID, with status, due date, and description shown |
| **Search** tasks | case-insensitive matching over titles and descriptions |
| **Update** status | move a task between `Todo`, `InProgress`, and `Done` |
| **Delete** tasks | safely, with clear success/failure feedback |
| **Persist** data | tasks survive closing the program, saved as a readable JSON file |
| **Recover** from failure | a missing or corrupted file never crashes the program |
| **Be tested** | with real unit tests you can run yourself |

It is deliberately small enough to understand completely, and rich enough to teach every habit a real application builder needs.

### The complete journey map

```text
PART I — UNDERSTANDING BEFORE CODING          (the thinking foundation)
 ├─ Chapter 1   What problem solving really means
 ├─ Chapter 2   The history: from ancient algorithms to C# 14
 └─ Chapter 3   What C# and .NET give you, and why use them
                     │
PART II — FIRST STEPS                        (get running today)
 ├─ Chapter 4   Install the tools and run your first program
 └─ Chapter 5   The universal 7-step problem-solving process
                     │
PART III — THE C# LANGUAGE, ONE STEP AT A TIME   (the toolbox)
 ├─ Chapter 6   Variables, types, and expressions   … memory and meaning
 ├─ Chapter 7   Input, output, and validation       … talking to the user
 ├─ Chapter 8   Decisions and repetition           … if / switch / loops
 ├─ Chapter 9   Methods                            … naming your solutions
 ├─ Chapter 10  Collections and algorithms          … many values at once
 ├─ Chapter 11  Complexity                          … choosing an algorithm
 ├─ Chapter 12  Debugging and testing              … finding and preventing bugs
 ├─ Chapter 13  Object-oriented problem solving    … organizing with types
 └─ Chapter 14  Files, JSON, exceptions, and time   … beyond the memory
                     │
PART IV — THE PROJECT: BUILDING TASK MASTER   (apply everything)
 ├─ Chapter 15  Design and the domain model
 ├─ Chapter 16  Persistence — the repository
 ├─ Chapter 17  Business logic — the manager service
 ├─ Chapter 18  The user interface
 └─ Chapter 19  Quality — fix, validate, test, refactor
                     │
PART V — TOWARD MASTERY                       (go beyond)
 ├─ Chapter 20  Advanced problem-solving techniques
 ├─ Chapter 21  From console program to production application
 └─ Chapter 22  The mastery roadmap
                     │
APPENDICES A–E — vocabulary, symbols, error decoder, checklist, CLI reference
```

---

## How to Use This Guide

### The learning loop

For every chapter, and honestly for the rest of your programming life, follow this loop:

1. **Read the idea.** Do not rush to the code. The code only makes sense once the idea is clear.
2. **Predict the result.** Before running any program in this guide, write down (on paper, or in a comment) what you *think* it will print. Prediction turns reading into active thinking.
3. **Type the code yourself.** Do not copy-paste. Typing builds the motor memory and forces you to notice every symbol — every `;`, every `{`, every capital letter.
4. **Run the code.** A compiler error is *feedback*, not failure. Every professional programmer sees compiler errors daily.
5. **Change one thing.** After it works, deliberately change one value, one condition, or one method name — and predict the new result before running. This is how understanding is built.
6. **Explain it aloud.** If you cannot explain a line to another person (or to a rubber duck), you do not own it yet.
7. **Solve the exercises without looking at the solution.** The struggle is the learning. The solution is there to *check* yourself, not to replace the attempt.

### What "mastery" means in this guide

Mastery does **not** mean memorizing every C# feature — nobody does that, not even the people who build C#. Mastery means that when an unfamiliar problem appears, you can:

- understand what is being asked and ask precise questions about inputs, outputs, and rules;
- split a large problem into smaller problems you can actually solve;
- choose an appropriate data structure and a reasonable algorithm;
- write clear C# code that another person can read;
- test normal cases, boundary cases, and invalid cases systematically;
- debug methodically instead of randomly changing things;
- explain and defend your design choices;
- improve a solution without breaking its behavior;
- and build, maintain, and extend a complete application.

### Recommended tools

You need exactly three things, all free:

- **The .NET SDK** — the compiler, the runtime, and the command-line tools. Chapter 4 covers installation step by step.
- **A code editor** — Visual Studio Code (lightweight, all operating systems), Visual Studio (full IDE, Windows), or JetBrains Rider (all operating systems). Any of them works with this guide.
- **A terminal** — Command Prompt / PowerShell / Windows Terminal on Windows, Terminal on macOS, or any shell on Linux.

Optionally, install **Git** so you can save versions of your work as you go. It is not required, but it is a habit worth forming early.

### Code style conventions used in this guide

So that nothing surprises you later, this guide consistently follows these conventions:

- Modern C# (the features available in every .NET release from .NET 6 onward — anything from 2021 to today works, including .NET 8, 9, and 10).
- `PascalCase` for types, methods, and public members (`TaskItem`, `ReadRequiredText`).
- `camelCase` for parameters and local variables (`filePath`, `nextId`).
- `_camelCase` with an underscore for private fields (`_tasks`, `_repository`).
- Meaningful names everywhere. You will never see a variable called `x` in this guide except to make a point about bad names.

---

## Table of Contents

- [Welcome — Read This First](#welcome--read-this-first)
  - [What this guide is](#what-this-guide-is)
  - [What you will build](#what-you-will-build)
  - [The complete journey map](#the-complete-journey-map)
- [How to Use This Guide](#how-to-use-this-guide)
  - [The learning loop](#the-learning-loop)
  - [What "mastery" means in this guide](#what-mastery-means-in-this-guide)
  - [Recommended tools](#recommended-tools)
  - [Code style conventions used in this guide](#code-style-conventions-used-in-this-guide)
- [Part I — Understanding Before Coding](#part-i--understanding-before-coding)
  - [Chapter 1: What Problem Solving Really Means](#chapter-1-what-problem-solving-really-means)
  - [Chapter 2: The History — From Ancient Algorithms to Modern C#](#chapter-2-the-history--from-ancient-algorithms-to-modern-c)
  - [Chapter 3: What C# and .NET Give You — and Why You Should Use Them](#chapter-3-what-c-and-net-give-you--and-why-you-should-use-them)
- [Part II — First Steps](#part-ii--first-steps)
  - [Chapter 4: Environment Setup and Your First Program](#chapter-4-environment-setup-and-your-first-program)
  - [Chapter 5: The Universal Problem-Solving Process](#chapter-5-the-universal-problem-solving-process)
- [Part III — The C# Language, One Step at a Time](#part-iii--the-c-language-one-step-at-a-time)
  - [Chapter 6: Variables, Types, and Expressions — Your Program's Memory](#chapter-6-variables-types-and-expressions--your-programs-memory)
  - [Chapter 7: Input, Output, and Validation — Talking to the User](#chapter-7-input-output-and-validation--talking-to-the-user)
  - [Chapter 8: Decisions and Repetition — Teaching the Program to Choose and Repeat](#chapter-8-decisions-and-repetition--teaching-the-program-to-choose-and-repeat)
  - [Chapter 9: Methods — Naming Your Solutions](#chapter-9-methods--naming-your-solutions)
  - [Chapter 10: Collections and Algorithms — Many Values at Once](#chapter-10-collections-and-algorithms--many-values-at-once)
  - [Chapter 11: Complexity — Choosing an Algorithm That Scales](#chapter-11-complexity--choosing-an-algorithm-that-scales)
  - [Chapter 12: Debugging and Testing — Finding Bugs Before Users Do](#chapter-12-debugging-and-testing--finding-bugs-before-users-do)
  - [Chapter 13: Object-Oriented Problem Solving — Organizing a Growing Program](#chapter-13-object-oriented-problem-solving--organizing-a-growing-program)
  - [Chapter 14: Files, JSON, Exceptions, and Time — Beyond the Memory](#chapter-14-files-json-exceptions-and-time--beyond-the-memory)
- [Part IV — The Project: Building Task Master](#part-iv--the-project-building-task-master)
  - [Chapter 15: Task Master Part 1 — Design and the Domain Model](#chapter-15-task-master-part-1--design-and-the-domain-model)
  - [Chapter 16: Task Master Part 2 — Persistence, the Repository](#chapter-16-task-master-part-2--persistence-the-repository)
  - [Chapter 17: Task Master Part 3 — Business Logic, the Manager Service](#chapter-17-task-master-part-3--business-logic-the-manager-service)
  - [Chapter 18: Task Master Part 4 — The User Interface](#chapter-18-task-master-part-4--the-user-interface)
  - [Chapter 19: Task Master Part 5 — Quality: Fix, Validate, Test, Refactor](#chapter-19-task-master-part-5--quality-fix-validate-test-refactor)
- [Part V — Toward Mastery](#part-v--toward-mastery)
  - [Chapter 20: Advanced Problem-Solving Techniques](#chapter-20-advanced-problem-solving-techniques)
  - [Chapter 21: From Console Program to Production Application](#chapter-21-from-console-program-to-production-application)
  - [Chapter 22: The Mastery Roadmap](#chapter-22-the-mastery-roadmap)
- [Appendices](#appendices)
  - [Appendix A — C# Vocabulary](#appendix-a--c-vocabulary)
  - [Appendix B — C# Symbols](#appendix-b--c-symbols)
  - [Appendix C — Compiler Error Decoder](#appendix-c--compiler-error-decoder)
  - [Appendix D — The Problem-Solving Checklist](#appendix-d--the-problem-solving-checklist)
  - [Appendix E — `dotnet` CLI Quick Reference](#appendix-e--dotnet-cli-quick-reference)
- [Final Message to the Learner](#final-message-to-the-learner)

---

## Part I — Understanding Before Coding

Most people believe programming is "typing code." It is not. Programming is **solving problems with precise thinking**, and the code is merely the written record of that thinking. Part I builds the mental foundation that every later chapter stands on: what a problem is, where this discipline came from, and what your tools (C# and .NET) actually give you.

---

### Chapter 1: What Problem Solving Really Means

> **In this chapter you will learn:** what a problem is, the five parts every programming problem has, the difference between an algorithm, a program, and an application, the difference between syntax and semantics, and how to write pseudocode — the thinking tool that professionals use before they write any code.
>
> **Prerequisites:** none. This chapter has no code at all — on purpose.

#### 1.1 Why this chapter comes first

Here is the single most common reason beginners give up on programming, and it is not what you think. It is not that C# is too hard, or that the computer is too fast, or that the tools are too complicated. It is this:

> They start by asking **"which keyword do I type?"** before they can say, in plain human words, **"what exactly must happen?"**

If you cannot describe the solution in plain language, no programming language can save you — because you have nothing to translate. So before we touch any keyboard, we learn to describe problems and solutions precisely. Every skill in this chapter will be used in every single chapter that follows.

#### 1.2 What is a problem?

A **problem** is a situation in which you want a specific result, but the path from where you are now to that result is not immediately known.

Notice the two halves of that definition:

- **You want a result.** ("I want to know the largest number in this list." "I want my tasks still there tomorrow." "I want to know if this password is acceptable.")
- **The path is unknown.** If you already knew the steps, it would not be a problem — it would be a habit.

Some everyday examples of problems:

- Find the largest number in a list of numbers.
- Decide whether a password is strong enough to be accepted.
- Calculate the total price of a shopping basket, including tax.
- Store your tasks so that they are still present tomorrow after the program restarts.
- Find the shortest route between two locations on a map.

Every one of these can be solved by following *precise instructions*. That is the definition of a **programming problem**: a question that can be answered by following precise, unambiguous, mechanical steps.

And here is the good news: a computer is a machine that follows precise, unambiguous, mechanical steps *extraordinarily well and extraordinarily fast*. The only catch — the entire discipline of programming in one sentence — is that **the steps must truly be precise and unambiguous, because the computer will do exactly what you say, not what you mean.**

#### 1.3 The five parts of every programming problem

Before writing one line of code for any problem, train yourself to answer five questions. Let's apply them to the task manager we will build later, so this is not abstract:

| Part | The question you must answer | Example: the task manager |
|---|---|---|
| **1. Input** | What information enters the program? | Task title, description, due date, menu choices, task IDs |
| **2. Output** | What result should the program produce? | A saved task, a displayed list, a success or error message |
| **3. Rules** | What must always be true? | A title cannot be empty; a task ID must be positive; a status must be one of three values |
| **4. Constraints** | What limits and dangers exist in the world outside the code? | The save file may not exist, may be corrupted, or may not be writable; the user may type anything |
| **5. Success measure** | How will we *know* the solution is correct? | A task created today still appears after restarting the program tomorrow |

Why each part matters:

- **Input** forces you to think about the boundary between your program and the outside world. Everything that crosses that boundary is *data you do not control* (Chapter 7 turns this instinct into code).
- **Output** forces you to define "done." Many beginner programs never truly finish because "finished" was never defined.
- **Rules** become your *validation* (Chapter 7) and your *invariants* (Chapter 20). A rule you cannot state is a rule you cannot enforce.
- **Constraints** are where programs die in the real world. The file doesn't exist. The disk is full. The user typed a smiley face where a number belonged. We handle these deliberately in Chapters 14 and 16.
- **The success measure** becomes your *test* (Chapter 12). If you cannot say how you would check correctness, you cannot check it.

#### 1.4 Algorithm, program, and application — three different words

These three words are related but **not** the same, and using them precisely will make everything you read from now on clearer:

- An **algorithm** is a finite sequence of steps for solving a problem — *independent of any programming language*. It can be written in English, drawn as a diagram, or scrawled on a napkin.
- A **program** is an algorithm *expressed in* a programming language, precisely enough that a computer can execute it.
- An **application** is a program *organized* to provide useful behavior to a user or another system: with an interface, persistent data, error handling, and structure that can grow.

Example — here is an algorithm for finding the largest number in a list:

1. Start with the first number as the current largest.
2. Look at each remaining number, one at a time.
3. If the number you are looking at is larger than the current largest, replace the current largest with it.
4. After looking at all numbers, the current largest is the answer.

Notice what this algorithm has:

- **Finiteness** — it ends (after looking at each number once).
- **Unambiguity** — "larger than" is a precise comparison.
- **A guarantee** — after step 4 you *know* you are correct, because every number was compared.

We will translate exactly this algorithm into C# in Chapter 6 and analyze its cost in Chapter 11.

#### 1.5 Syntax and semantics

Two words you will meet constantly:

- **Syntax** is the *grammar* of a programming language: which arrangements of symbols are legal. Just as "the cat sat on the mat" is grammatical English and "sat the mat on cat the" is not, code has grammar rules.
- **Semantics** is the *meaning* of grammatically legal code: what it actually does when run.

Three examples make the difference permanent:

This is **syntactically valid** C#:

```csharp
int age = 20;
```

Read it word by word: `int` (a whole number type) — `age` (a name we chose) — `=` (assignment: put the right side's value into the left side's box) — `20` (the value) — `;` (the statement ends here).

This is **syntactically invalid**:

```csharp
int = age 20;
```

The words are the same, but the arrangement breaks C#'s grammar. A program containing this line **will not run at all** — the compiler refuses it. You will see an error like `CS1002 ; expected` or `CS1525 Invalid expression term '='`. Errors like this are *good*: the compiler caught a mistake before the program could even start.

This is **syntactically valid but logically wrong**:

```csharp
int yearsUntilRetirement = 20 - age;
```

If `age` is 40, this computes `-20`. The compiler has no idea whether that is a mistake, because *grammatically* it is a perfectly formed subtraction. It matches no rule of the language — but it violates the *intention* of the program. Programs can only be caught doing this by **testing** (Chapter 12) and **reasoning** (this chapter).

The lesson: syntax errors are trivial and the compiler finds them for free. The dangerous errors are the ones where the code is grammatically perfect but does the wrong thing. That is why we think *before* typing.

#### 1.6 Pseudocode: thinking on paper

**Pseudocode** is a solution written in structured plain language — no syntax rules, but shaped like an algorithm. It is the bridge between "I vaguely want an app" and "here is the exact behavior."

Example — pseudocode for adding a task to the task manager:

```text
ask the user for a task title
if the title is empty
    show an error and stop
otherwise
    ask for an optional description
    ask for an optional due date
    create a new task with the title, description, and due date
    save all tasks to the file
    show a success message
```

Why pseudocode works:

1. **It exposes missing decisions early.** While writing it you discover the questions you forgot to ask: What if the user types only spaces? What date format will we accept? Should saving happen immediately or on exit?
2. **It is cheap to change.** Rewriting five lines of pseudocode takes seconds. Rewriting a program's structure takes hours.
3. **It is language-independent.** The pseudocode above could be implemented in C#, Python, Java, or anything else — because the *thinking* is done.
4. **It becomes a review checklist.** After coding, you compare the program against the pseudocode line by line. This is the simplest code review technique that exists.

Style rules for good pseudocode:

- One action per line.
- Indentation shows what belongs inside what (just like it will in C#).
- Use consistent vocabulary — "show", "ask", "save" — not a random mix of synonyms.
- Never include language syntax like `;` or `{}`. The moment pseudocode contains syntax, it stops being thinking and starts being typing.

#### 1.7 A complete worked example: from vague to precise

Watch the transformation that every real project goes through. Here is a vague request:

> "Make me a task app."

That is not a problem yet — it is a wish. Apply the five parts:

| Part | Analysis |
|---|---|
| **Input** | Task title (text), optional description (text), optional due date (date), menu choice (number), task ID (number) |
| **Output** | Confirmations, the task list, search results, clear error messages |
| **Rules** | Title required; IDs unique and positive; status limited to Todo / InProgress / Done; search ignores letter case |
| **Constraints** | Program must survive a missing or corrupted save file; must run on Windows, macOS, and Linux; must work in a plain terminal with no internet |
| **Success measure** | Create a task, close the program, reopen it — the task is still there. Delete the task — it stays gone after restart. Corrupt the save file — the program starts empty with a friendly message instead of crashing. |

And now a precise sentence that could be handed to a developer:

> "Allow a user to create a task with a non-empty title, an optional description, and an optional due date; list, search, update, and delete tasks; persist all data to a local JSON file; and recover gracefully from a missing or corrupted file."

That sentence *is* the seed of the application we build in Part IV. This is not a coincidence — this guide practices exactly what it teaches.

#### 1.8 The single most important habit

Here is the habit, stated once, that separates people who become programmers from people who bounce off:

> **Separate understanding from implementation.** First write the steps in plain language. Only when the steps are clear do you translate them into C#.

When you feel stuck on any problem in your future — and you will — do not stare at the code. Stand up, and say out loud, in plain words, what must happen. If you cannot say it, you have found the real problem: not the code, the understanding. Fix that first, and the code will almost write itself.

#### 1.9 Exercises

Do these before moving on. Writing answers in full sentences is part of the training.

1. Describe the input, output, rules, constraints, and success measure for a **calculator** program.
2. Write pseudocode for checking whether a number is even. (Hint: a number is even when dividing it by 2 leaves no remainder.)
3. Write pseudocode for finding the smallest number in a list.
4. Describe a real-world everyday process (cooking, laundry, boarding a plane) as an algorithm, and identify one input, one output, and one rule it enforces.

<details>
<summary><b>Solutions — open only after you have written your own answers</b></summary>

**1. Calculator — the five parts:**

- *Input:* two numbers, an operation to perform (`+`, `-`, `*`, `/`).
- *Output:* the numeric result, or an error message.
- *Rules:* division by zero must not crash — it must produce an error message; numbers must be parseable as real numbers.
- *Constraints:* the user may type letters, nothing at all, or enormous values; the program has no memory of previous calculations (keep v1 simple).
- *Success measure:* entering `8`, `*`, `7` shows `56`; entering `5`, `/`, `0` shows an error and the program keeps running.

**2. Even check — pseudocode:**

```text
ask the user for a number
divide the number by 2 and keep only the remainder
if the remainder is 0
    report that the number is even
otherwise
    report that the number is odd
```

**3. Smallest number — pseudocode:**

```text
start with the first number as the current smallest
look at each remaining number one at a time
if the current number is smaller than the current smallest
    replace the current smallest with it
after all numbers are examined, the current smallest is the answer
```

(Notice this is the largest-number algorithm with the comparison flipped — reusing a known solution by changing one detail is a core problem-solving move called *analogy*.)

**4. Example — cooking pasta as an algorithm:**

- *Input:* dry pasta (an amount), water, salt, heat.
- *Output:* cooked pasta.
- *One rule:* water must be boiling *before* the pasta enters — the order of steps is part of the recipe, exactly as order of steps is part of an algorithm.
- *Steps:* fill a pot, bring water to a boil, add salt, add pasta, wait until cooked, drain. Each step has a condition ("until boiling", "until cooked") — real algorithms are full of conditions like this, and Chapter 8 teaches you to write them.

</details>

---

### Chapter 2: The History — From Ancient Algorithms to Modern C#

> **In this chapter you will learn:** that problem solving is thousands of years older than computers, who invented the key ideas (with names you should know), how programming languages evolved from raw machine numbers to modern C#, and the complete version history of C# — so that when you read "C# 12" or ".NET 10" somewhere, you know exactly what it means.
>
> **Prerequisites:** Chapter 1.

#### 2.1 Why history matters (this is not filler)

Three practical reasons:

1. **It removes intimidation.** When you struggle, it helps to know that the greatest minds in this field struggled with the same fundamentals — variables, conditions, loops, decomposition. You are learning what humanity refined over millennia, compressed into a few months.
2. **It explains why the tools are shaped the way they are.** Why does C# look like C and Java? Why does .NET exist? Why is *everything* about "managing complexity"? History answers all three.
3. **It future-proofs you.** Languages die; the skill of turning vague goals into precise steps is immortal. Watching that pattern across history teaches you to learn skills, not syntax.

#### 2.2 The ancient world: procedures before machines

Problem solving is older than computers by thousands of years. Humans have always needed repeatable procedures for counting, measuring, taxing, building, and predicting the seasons and the skies.

- **Euclid's algorithm** (around 300 BC, in the *Elements*, Book VII) finds the greatest common divisor of two numbers by repeatedly replacing the pair with smaller pairs based on remainders. It is still taught today, still executes on real hardware, and is a beautiful example of an algorithm that is *provably correct and finite* — 2,300 years before the first computer existed.
- **Muhammad ibn Musa al-Khwarizmi** (c. 780–850), working in the House of Wisdom in Baghdad, wrote systematic, step-by-step procedures for solving equations. Two words in computing trace directly back to him:
  - his Latinized name, *Algoritmi*, became the word **algorithm**;
  - the title of his book on solving equations — *al-jabr* ("the reunion of broken parts") — became the word **algebra**.

So when you "write an algorithm," you are literally invoking a 1,200-year-old tradition of writing solutions as mechanical, reusable steps. The word itself tells you what the discipline values: *procedures that work the same way every time*.

#### 2.3 The mechanical dream: Babbage and Lovelace

In the nineteenth century, the dream became metal.

- **Charles Babbage** designed the **Difference Engine** (a machine for computing tables of numbers automatically) and then the far more ambitious **Analytical Engine** — a general-purpose mechanical computer, designed in the 1830s–1840s, with a "store" (memory), a "mill" (processor), and punched-card input inspired by the Jacquard loom. It was never completed in his lifetime, but the *concept* of a general-purpose computing machine was born.
- **Ada Lovelace** (1815–1852), translating and annotating a description of the Analytical Engine in 1843, wrote what is widely regarded as the first published algorithm intended for a machine — a procedure for computing the Bernoulli numbers. Her famous insight was ahead of its time: the machine could manipulate not only numbers but *symbols* — that it could, in principle, compose music or manipulate anything that could be encoded. That is the first recorded glimpse of *software*.

Why this matters to you: the Analytical Engine's architecture — memory, processor, input, output — is *still* the shape of every computer you will ever run your C# programs on, including the one reading this file.

#### 2.4 Can everything be computed? Turing and Church

By the twentieth century, a deeper question appeared, and mathematics tried to answer it:

> Which problems can be solved by *any* mechanical procedure at all?

- **Alan Turing** (1936, in his paper *On Computable Numbers*) defined an abstract machine — now called the **Turing machine** — that reads and writes symbols on an infinite tape according to simple rules, and proved precise things about what such machines can and cannot compute.
- **Alonzo Church** developed the **lambda calculus**, a mathematical language for functions, around the same time.
- The shared conclusion, now called the **Church–Turing thesis**, remains the foundation of computer science: every effectively computable process can be expressed in these simple models.

The practical echo of this theory reaches you in this guide in two ways: (1) the confidence that *if* a problem can be solved by steps at all, a program can express those steps; and (2) the humility that *some* problems provably cannot be solved by any program — which is why "prove it possible" is a real step in professional problem solving, not paranoia.

#### 2.5 From machine code to modern languages

The first electronic computers (like ENIAC, completed 1945) were *programmed* by physically rewiring them. Then came generations of abstraction, each one hiding painful details so humans could think about the *problem* instead of the *machine*:

| Generation | What it looked like | What it hid | Era (approx.) |
|---|---|---|---|
| 1. Machine code | Raw binary numbers: `01001010 11010101` | Nothing — pure hardware | 1940s–50s |
| 2. Assembly | Short mnemonics: `MOV AX, 5` | Raw binary encoding | 1950s– |
| 3. Procedural languages | `FORTRAN` (1957), `COBOL` (1959), `C` (1972) | CPU registers, memory addresses | 1957– |
| 4. Object-oriented languages | `Smalltalk` (1980), `C++` (1985), `Java` (1995) | Hardware-specific structure, memory discipline | 1980s– |
| 5. Managed runtime languages | C#, running on the .NET CLR (2002) | Manual memory management, platform differences | 2002– |
| 6. Modern multi-paradigm | C# today: OOP + functional + async + pattern matching | Whatever you are not currently thinking about | now |

Two milestone names worth knowing in that ladder:

- **Grace Hopper** wrote the first *compiler* (the A-0 system, 1952) — the idea that a program could translate human-friendly code into machine code was itself once considered nearly impossible. Every C# compiler you will ever use is her idea, industrialized.
- **Dennis Ritchie's C** (1972, Bell Labs) became the ancestor of C++, Java, JavaScript's syntax, and C#. When you write `int`, you are holding a fossil from 1972 — kept because it was a good idea.

Every generation follows the same principle — **abstraction**: hide the details you do not need, so you can focus on the problem you do need. C# is one of the most complete expressions of that principle in mainstream use.

#### 2.6 The history of C# itself

C# was created at **Microsoft** in the late 1990s–2000, led by **Anders Hejlsberg** — who had previously built **Turbo Pascal** and **Delphi**, two of the most respected developer tools ever made. Hejlsberg wanted a language with C-style readability, Java-like safety, Delphi-like productivity, and stronger type discipline than either.

Fun fact about the name: "**C#**" is spoken as "C sharp." In music, a *sharp* raises a note by a semitone — and the symbol `#` itself is drawn as four `+` signs stacked together: C# as "C++ incremented, once more." The joke is also a mission statement: take what came before and improve it.

The release history — every version listed here is real and dated; you will meet features from all of them in this guide:

| Version | Released with | Year | Headline features you will actually use in this guide |
|---|---|---|---|
| C# 1.0 | .NET Framework 1.0 | 2002 | The language itself: classes, methods, types, `foreach` |
| C# 2.0 | .NET Framework 2.0 | 2005 | **Generics** — `List<T>`, `Dictionary<TKey,TValue>` (Chapter 10) |
| C# 3.0 | .NET Framework 3.5 | 2007 | **LINQ** and lambda expressions (Chapters 10, 17), `var` |
| C# 4.0 | .NET Framework 4 | 2010 | `dynamic`, named/optional arguments |
| C# 5.0 | .NET Framework 4.5 | 2012 | **`async` / `await`** (Chapter 20) |
| C# 6 | .NET Framework 4.6, Roslyn | 2015 | **String interpolation** `$"..."` (Chapters 6, 18), `nameof`, null-conditional `?.` |
| C# 7 | .NET Framework 4.7 | 2017 | `out var`, tuples, pattern matching begins |
| C# 8 | .NET Core 3.x | 2019 | **Nullable reference types** (`string?` — Chapters 7, 14), switch expressions |
| C# 9 | .NET 5 | 2020 | **Top-level statements** (Chapter 4), target-typed `new()` (used everywhere), `record` |
| C# 10 | .NET 6 | 2021 | **File-scoped namespaces** (Chapters 15–18), global usings |
| C# 11 | .NET 7 | 2022 | `required` members, raw string literals |
| C# 12 | .NET 8 | 2023 | Primary constructors, collection expressions |
| C# 13 | .NET 9 | 2024 | `params` collections, new `lock` type |
| C# 14 | .NET 10 | 2025 | Extension members and other refinements |

The platform's history matters just as much as the language's:

- **2002:** C# 1.0 ships with .NET Framework 1.0 — but the Framework runs **only on Windows**.
- **2004–2016:** The **Mono** project (led by Miguel de Icaza) reimplements .NET for Linux and macOS, proving the demand for C# beyond Windows. Mono's successor company, **Xamarin**, is acquired by Microsoft in 2016.
- **2014–2015:** Microsoft open-sources the C# compiler itself — rewritten from the ground up in C#, and named **Roslyn** — founding the .NET Foundation in 2014. The compiler of C# became a C# program.
- **2016:** **.NET Core 1.0** — a completely new, open-source (MIT), cross-platform .NET built from the ground up. C# programs now run natively on Windows, macOS, and Linux.
- **2020:** **.NET 5** unifies .NET Core and the legacy .NET Mono lineage under one name — no more "Core" suffix, one modern platform.
- **Today:** .NET is developed in the open on GitHub. A new major version ships **every November**: even-numbered versions are **LTS** (long-term support, 3 years of fixes), odd-numbered are STS (18 months). **.NET 10 (November 2025)** is the current LTS release and the version this guide targets; any .NET from 6 onward runs every example in this guide.

#### 2.7 What the history teaches

Pull the thread of 2,300 years and one lesson repeats:

- Euclid wrote steps. al-Khwarizmi wrote steps. Lovelace wrote steps for a machine that did not exist yet. Turing defined what steps can achieve. Hopper made the machine *understand* our steps. Hejlsberg made the steps safer to write.
- **Languages change constantly — the core skill never has.** Turning a vague goal into precise steps is the permanent, transferable, human half of programming. The language (today C#, tomorrow something else) is only the notation.

That is why this guide spends its first chapters on thinking, not typing — and why what you build here will survive every future language you learn.

---

### Chapter 3: What C# and .NET Give You — and Why You Should Use Them

> **In this chapter you will learn:** the difference between C#, .NET, the CLR, IL, and the SDK (words that confuse everyone at first); what actually happens when your code runs; what C# provides you as a problem solver; what you can build with it; why it is an excellent first language for learning problem solving; and — importantly — what it can *never* do for you.
>
> **Prerequisites:** Chapters 1–2.

#### 3.1 The words: C#, .NET, CLR, IL, SDK, NuGet

Beginners constantly mix these five names up, so we define them once, precisely:

| Word | What it actually is | Analogy |
|---|---|---|
| **C#** | The *programming language* — the vocabulary and grammar you write source code in. Files ending in `.cs`. | The language a book is written in |
| **.NET** | The *platform* — the runtime that executes your code, plus the enormous standard library, plus the tools and project system. | The publishing house, library system, and distribution network |
| **CLR** | The **C**ommon **L**anguage **R**untime — the part of .NET that actually runs your program: loads it, verifies it, manages its memory, enforces its types. | The printing press + the reading rooms |
| **IL** | **I**ntermediate **L**anguage — the compiled form of your C#, a CPU-independent instruction set that the CLR understands. Also called *managed code*. | The typeset plates from which any number of books can be printed |
| **SDK** | The **S**oftware **D**evelopment **K**it — everything you install: compilers, the CLR, libraries, and the `dotnet` command-line tool. | The author's complete toolkit |
| **NuGet** | The package manager for .NET — how you download libraries other people published. | The bookstore for reference works |

The one-sentence version to memorize:

> **You write C#. The SDK compiles it to IL. The CLR executes the IL. The .NET libraries fill in almost everything else.**

#### 3.2 What actually happens when you run a C# program

This pipeline explains every strange thing beginners observe (why there is a "build" step, why the first run is slow, what "compilation error" means):

```text
   You write:            Program.cs
        │
        ▼  dotnet build  (C# compiler, Roslyn)
   Compiled to:          IL (Intermediate Language) inside a .dll file
        │
        ▼  dotnet run    (the CLR loads it)
   Runtime:              The JIT compiler translates IL → real machine
                         instructions for YOUR specific CPU and OS
        │
        ▼
   Result:               the running program, with memory managed,
                         types checked, and the .NET library available
```

Step by step:

1. **You write C#** — human-readable text in `.cs` files.
2. **`dotnet build` compiles it.** The compiler checks every rule of the language (this is where syntax errors appear), then translates your code into **IL** — a compact, CPU-independent instruction language. This is *why* C# can run on Windows, macOS, and Linux from the same compiled file: the file does not target a CPU; it targets the CLR.
3. **`dotnet run` starts the CLR.** The CLR loads your IL and hands it to the **JIT** (just-in-time) compiler, which translates each part into genuine machine instructions for your exact processor — an Intel chip on a laptop, an ARM chip in a cloud server — at the moment it is first needed.
4. **The CLR babysits your program the whole time.** It allocates memory when you create objects and reclaims it automatically when you stop using them (**garbage collection** — the reason you will never write "free this memory" in this guide). It verifies types, so a `string` can never secretly pretend to be an `int`. It gives you the entire .NET library: files, networking, JSON, dates, text, math, collections.
5. **The program ends**, and the CLR cleans everything up.

Why this design is a gift to you: entire categories of bugs that haunted C programmers for decades — using memory after freeing it, forgetting to free it at all, pointers pointing at the wrong thing — are *structurally impossible* in C#. You get to spend your attention on the problem instead of the machine.

#### 3.3 What C# provides you, feature by feature

Here is what is in the box, and why each item matters to a problem solver:

- **Readable, C-family syntax.** `if`, `for`, `while`, `{ }` — the same grammar shared by C, C++, Java, and JavaScript. Learn it once, and you can read four of the world's top ten languages.
- **Strong static typing.** Every value has a type, known and checked *before the program runs*. A typo like `tite` instead of `title` becomes a compile-time error, not a runtime crash three weeks later. The compiler becomes your pair programmer.
- **Automatic memory management.** Create objects freely; the CLR reclaims them. No manual bookkeeping.
- **A gigantic, coherent standard library.** Reading files, parsing JSON, handling dates, LINQ over collections, HTTP, cryptography — batteries very much included.
- **Generics.** One `List<T>` that stores *any* type safely (`List<int>` of numbers, `List<TaskItem>` of tasks) — one algorithm, zero type holes.
- **Object-oriented *and* functional features.** Classes, interfaces, and inheritance for organizing big systems; lambdas and LINQ for expressing data transformations in a line.
- **`async` / `await`.** The cleanest mainstream answer to a genuinely hard problem: waiting for slow things (disk, network) without freezing your program.
- **Nullable annotations (`string?`).** The compiler warns you when you might be handling a "no value" case incorrectly — null-related bugs are the billion-dollar mistake of computing, and modern C# fights them with you.
- **World-class tooling.** The Roslyn compiler is itself open source and written in C#; debuggers, profilers, formatters, and test runners are integrated everywhere.

#### 3.4 What you can build with C#

C# is a general-purpose language running on a general-purpose platform. With the core skills from this guide you can later build:

- **Web applications and HTTP APIs** (ASP.NET Core) — the backend behind many of the services you use daily
- **Cross-platform desktop apps** (WPF, Avalonia, MAUI)
- **Mobile apps** for Android and iOS (.NET MAUI)
- **Games** — Unity, one of the two dominant game engines in the world, uses C# as its scripting language
- **Cloud services and serverless functions** (Azure, AWS)
- **Command-line tools** — what you will build here
- **Data processing, automation, and integration scripts**
- **Libraries** shared with other developers via NuGet

#### 3.5 Why C# is a *good choice for learning problem solving* specifically

Many languages could teach you syntax. C# has specific advantages for the skill this guide actually targets:

1. **It refuses to guess.** Python will happily run `age = "twenty"` and explode later. C# says *no* at compile time. For a learner, early loud errors are a superpower — they teach the discipline of precision at the exact moment you form your habits.
2. **It is explicit about types, so you learn what data *is*.** Understanding that `17`, `"17"`, and `17.0` are three different things *in memory* is half of programming. C# makes you confront this from day one.
3. **The error messages teach.** `CS0104 'X' is an ambiguous reference between 'A' and 'B'` tells you what, where, and why. Reading compiler output is a trainable skill, and C# output is among the most readable of any language.
4. **The upgrade path is smooth.** The console app you build here scales up to web APIs, services, and games without changing languages.
5. **It is mainstream and hired for.** C# is a top-10 language in industry usage rankings, with strong demand in enterprise, fintech, healthcare, gaming, and government.

#### 3.6 An honest comparison with other beginner languages

| Question | C# | Python | Java | JavaScript |
|---|---|---|---|---|
| First-day simplicity | More ceremony than Python | Simplest | More ceremony | Simple |
| Types catch errors early? | Yes, compile time | No, runtime mostly | Yes | Barely |
| Real applications beyond scripts? | Very strong (web, desktop, games, cloud) | Strong (web, data, AI) | Very strong (enterprise, Android) | Web is its kingdom |
| Same language from CLI to web API? | Yes | Mostly | Yes | Mostly |
| Debugging/tooling quality | Excellent | Good | Excellent | Varies |

This is not a ranking — Python is a fine first language too. The point is that C# pays you back for its extra strictness with safety, speed, and reach, which is why this guide chose it.

#### 3.7 What C# can never do for you

This section is the most important in the chapter. A language cannot:

- **decide your requirements** — is an empty title allowed? what does "high priority" mean? must dates be UTC? *You* must decide, and write it down;
- **know your real-world constraints** — file formats, network flakiness, time zones, legal rules;
- **choose your algorithms** — the language provides `List`, `Dictionary`, sorting, searching; *you* must choose the one that fits;
- **guarantee correctness** — a program that compiles can still be wrong (Chapter 1: semantics vs syntax);
- **test your judgment** — whether duplicate tasks are legal is a *business decision* nobody can compile.

> **The language provides tools. You provide the reasoning.** Everything in Parts I and II of this guide is about the reasoning; the language chapters simply hand you the tools.

#### 3.8 Exercises

1. In your own words — one sentence each — define: C#, .NET, CLR, IL, SDK.
2. A friend says "C# only runs on Windows." Using history from Chapter 2, explain precisely why that is outdated, and what changed and when.
3. You write a program that compiles without errors but prints the wrong total. Which category is this error (syntax, runtime, or logic), and which chapter of this guide will give you the tools to find it?
4. Name one thing a compiler can check for you and one thing it fundamentally cannot.

<details>
<summary><b>Solutions</b></summary>

**1.** C#: the programming language you write. .NET: the platform — runtime + libraries + tools. CLR: the execution engine inside .NET that runs IL, manages memory, and checks types. IL: the CPU-independent instruction language your C# is compiled to. SDK: the installed toolkit (compilers, runtime, libraries, `dotnet` CLI).

**2.** It was true of the original .NET Framework (2002). Mono (2004+) brought it to Linux/macOS; .NET Core 1.0 (2016) made cross-platform official and first-class; .NET 5 (2020) unified everything into one open-source platform. Today C# programs run natively on Windows, macOS, and Linux.

**3.** A logic error — grammatically valid code doing the wrong thing. Chapter 12 (debugging and testing) provides the systematic tools; the habit of stating expected results *before* running (Chapter 1) is what makes such errors visible at all.

**4.** A compiler checks *syntax and types* — that `age` is an `int` and you never assign a `string` to it. It cannot check *intent* — whether `20 - age` was supposed to compute years until retirement (vs. producing `-20` when age is 40). Intent requires the success measures, tests, and reasoning of Chapters 1, 5, and 12.

</details>

---

## Part II — First Steps

Understanding is built. Time to touch a keyboard. In Part II you install the tools, run your first program, and acquire the universal 7-step process that will drive every problem you solve from now on — including the application you build in Part IV.

---

### Chapter 4: Environment Setup and Your First Program

> **In this chapter you will learn:** how to verify and install the .NET SDK; how to create, build, and run a project with the `dotnet` command — with every word of every command explained; what the project template creates for you (including reading your `.csproj` file line by line); how to write and fully understand `Console.WriteLine("Hello, problem solver!")` down to the individual symbols; how to write comments; and how to read your first compiler errors.
>
> **Prerequisites:** nothing technical. A computer with internet access once.

#### 4.1 The tool check

Open a terminal: **Windows Terminal / PowerShell** (Windows), **Terminal** (macOS), or your preferred shell (Linux). Then type this exact command and press Enter:

```bash
dotnet --version
```

Word by word:

- `dotnet` — the .NET command-line driver. If it is installed, this single word opens the door to every .NET tool.
- `--version` — an *option* (also called a *flag*): it changes the driver's behavior. This one asks: "print the installed SDK version and stop."
- Pressing Enter — the terminal hands the line to the shell, the shell finds the `dotnet` program, and runs it.

Possible results:

1. **A version number prints** (for example `10.0.x` — some build of .NET 10, or `8.0.x`, `9.0.x`). You are ready. Skip to 4.3.
2. **"command not found"** or "'dotnet' is not recognized"** — the SDK is not installed (or a newly installed one needs a fresh terminal). Install it next.

#### 4.2 Installing the .NET SDK

Go to the official site — **https://dotnet.microsoft.com/download** — and download the current **.NET SDK** (not "runtime": the runtime only *runs* programs; the SDK *builds* them — Chapter 3's distinction in practice). Choose your operating system, run the installer, and when it finishes, **open a completely new terminal** (important: the old one memorized the old state) and run `dotnet --version` again. A number should appear.

That number is your SDK version. Everything in this guide works with .NET 6 or newer; the current long-term-support (LTS) version is .NET 10.

#### 4.3 Choose an editor (any of these is fine)

- **Visual Studio Code** — free, lightweight, works on Windows/macOS/Linux. Install the official **C# Dev Kit** extension and you get IntelliSense (completion as you type), debugging, and project awareness.
- **Visual Studio** (Windows) — the full IDE; heavier, but the debugger is legendary. The free Community edition is enough.
- **JetBrains Rider** — cross-platform IDE; free for non-commercial use.

All screenshots in your future will differ; all commands in this guide work identically everywhere, because we use the `dotnet` command line.

#### 4.4 Create your first project

In your terminal, navigate to wherever you keep projects (or create a folder), then run these three commands:

```bash
dotnet new console -n ProblemSolvingJourney
cd ProblemSolvingJourney
dotnet run
```

Command by command, word by word:

- **`dotnet new console -n ProblemSolvingJourney`**
  - `dotnet` — talk to the .NET toolchain.
  - `new` — create something **new** from a template.
  - `console` — *which* template: a console application — a plain text program that runs in the terminal. The perfect classroom: no buttons, no windows, no distractions from logic.
  - `-n` — short for **name**: the next word will be the project's name.
  - `ProblemSolvingJourney` — the name. This becomes both the folder name and a name inside the project file.
- **`cd ProblemSolvingJourney`** — **c**hange **d**irectory: move your terminal *into* the new folder so subsequent commands act on it.
- **`dotnet run`** — build the project (compile C# → IL) and immediately run the result. Your first full cycle of the entire pipeline from Chapter 3.

If you saw `Hello, World!` print, you have just executed a complete C# program on your machine.

#### 4.5 What the template created — read every file

Run `ls` (macOS/Linux) or `dir` (Windows) inside the project folder. Then open the folder in your editor. You should find:

```text
ProblemSolvingJourney/
├── Program.cs          <- your code (the interesting file)
├── ProblemSolvingJourney.csproj   <- the project definition
├── bin/                <- build output (machine-targeted artifacts) — generated, ignore
└── obj/                <- compiler intermediates — generated, ignore
```

**`Program.cs`** contains, in modern templates, exactly one line:

```csharp
Console.WriteLine("Hello, World!");
```

Two things to know about this one line:

- There is no `Main`, no class, nothing else. This is a C# 9+ feature called **top-level statements**: for small programs, the compiler quietly wraps your statements in a generated `Main` method for you. Convenient — but you should know the "real" shape exists, because Part IV uses it: a C# program traditionally has an entry point:

  ```csharp
  using System;

  class Program
  {
      static void Main()
      {
          Console.WriteLine("Hello, World!");
      }
  }
  ```

  **Execution begins at `Main`.** The runtime looks for that method and runs it, top to bottom. Top-level statements are just that structure, hidden. In this guide, small experiments (Chapters 6–14) use top-level statements for brevity; the real application (Part IV) uses the explicit form so you learn both.

- Modern templates also enable two project-level conveniences, defined in the **`.csproj`** — the XML file that describes the project. Open it; it reads:

  ```xml
  <Project Sdk="Microsoft.NET.Sdk">

    <PropertyGroup>
      <OutputType>Exe</OutputType>
      <TargetFramework>net10.0</TargetFramework>
      <ImplicitUsings>enable</ImplicitUsings>
      <Nullable>enable</Nullable>
    </PropertyGroup>

  </Project>
  ```

  Line by line:

  - `<Project Sdk="Microsoft.NET.Sdk">` — "this file describes a project, built with the standard .NET build toolkit."
  - `<OutputType>Exe</OutputType>` — build a runnable **exe**cutable (the alternative is a library for other programs to use).
  - `<TargetFramework>net10.0</TargetFramework>` — the .NET version this project targets: `net10.0` = .NET 10. Your file may show `net8.0` or `net9.0` — everything in this guide works on any of them.
  - `<ImplicitUsings>enable</ImplicitUsings>` — automatically add the most common `using` declarations (like `using System;`) to every file. This is why `Console.WriteLine` works in `Program.cs` without any visible `using`.
  - `<Nullable>enable</Nullable>` — turn on null-safety checking: the compiler will *warn* you when you might dereference "no value" (Chapters 7 and 14 turn this into a superpower).

You do not need to memorize this file — you need to *recognize* it. When a tutorial says "target framework," this is where it lives.

#### 4.6 Your first line of code, word by word

Change `Program.cs` to this (replace the whole content), then run with `dotnet run`:

```csharp
Console.WriteLine("Hello, problem solver!");
```

Now the full anatomy, because this one line contains nearly every concept of syntax you will reuse thousands of times:

| Symbol / word | What it is | What it means here |
|---|---|---|
| `Console` | A **class** from the .NET library | "the terminal window" — everything the program can do with the console lives here |
| `.` | Member access operator | "look *inside* `Console` and use one of its members" |
| `WriteLine` | A **method** (named behavior) belonging to `Console` | "write the text I give you, then move to a new line" |
| `(` `)` | Argument list | "here are the values the method needs" — the method's inputs travel inside parentheses |
| `"Hello, problem solver!"` | A **string literal** — text between double quotes | The exact characters to print. The quotes are not printed; they *delimit* the text |
| `;` | Statement terminator | "this instruction is complete." Nearly every C# statement ends with a semicolon |

Execution, step by step:

1. The program starts (at the generated `Main`, wrapping our top-level statement).
2. The runtime finds the class `Console` (already loaded from the .NET library).
3. It calls the method `WriteLine`, handing it the string `"Hello, problem solver!"`.
4. `WriteLine` sends the characters to the terminal and appends a line break.
5. There are no more statements; `Main` returns; the program ends. (Notice how instantly it all happened — that speed is why step-by-step reasoning, not "watching," is how we understand programs.)

Two sibling methods worth knowing immediately:

- `Console.Write(...)` — prints **without** the trailing line break.
- `Console.WriteLine(...)` — prints **with** the trailing line break.

And printing *several* lines just stacks calls:

```csharp
Console.WriteLine("Line one.");
Console.WriteLine("Line two.");
```

#### 4.7 Comments — notes to humans

A **comment** is text the compiler deliberately ignores — notes for yourself and other readers.

```csharp
// This is a single-line comment. It ends at the end of the line.

Console.WriteLine("The program is running.");  // trailing comments also work

/*
   This is a multi-line comment.
   Everything between the slash-star and star-slash is ignored,
   no matter how many lines it covers.
*/
```

Word by word: `//` — "ignore the rest of this line." `/*` … `*/` — "ignore everything between these markers."

Professional habits about comments:

- **Explain why, not what.** `int age = 25; // set age to 25` is noise. `int retirementAge = 65; // national default, configurable per country` is signal.
- Comments do not substitute for clear names (Chapter 9).
- You will also meet a third form, **XML documentation comments** (`///`), in professional code — machine-readable documentation attached to methods. Mentioned only so you recognize it; not needed in this guide.

#### 4.8 Meet the compiler — on purpose

Programming is not typing; it is a conversation with a very strict teacher. Let's start the conversation deliberately. Change your program to:

```csharp
Console.WriteLine("Hello, problem solver!"
```

…the same line without the final semicolon — and run `dotnet run`. You will see something like:

```text
Program.cs(1,42): error CS1002: ; expected
```

Read it like a pro, word by word:

- `Program.cs(1,42)` — **where**: file `Program.cs`, line 1, around column 42. The compiler reports the first position where it noticed something was impossible.
- `error` — the severity. (You will also meet `warning`: the program still runs, but you should look at it.)
- `CS1002` — the error **code**. C# errors all have `CS` numbers — Appendix C collects the ones beginners hit most.
- `; expected` — **what** the compiler concluded: at that spot, the grammar demands a semicolon.

Fix the line (restore the `;`) so the error disappears, and notice the deeper lesson: **the compiler is not scolding you; it is your first and most tireless test** — checking thousands of rules about every line you write, before the program can even run. Programmers read these messages all day. The ones who progress fastest are the ones who read them carefully instead of panicking.

#### 4.9 Your first modification exercise

Make the program print, using three separate `Console.WriteLine` calls:

1. your name;
2. your current learning goal;
3. one reason you want to learn problem solving.

Then — the real exercise — *before running it*, predict exactly what will appear, top to bottom. Run and check. If your prediction was wrong, congratulations: you just found a gap between your mental model and reality, which is the single most valuable thing a practice session can produce.

<details>
<summary><b>Solution (shape only — your words will differ)</b></summary>

```csharp
Console.WriteLine("My name is Maya.");
Console.WriteLine("My goal: build my own task manager in C#.");
Console.WriteLine("Reason: I want to automate my daily planning.");
```

Expected output before running — three lines, in exactly the order written, each on its own line. Programs run statements top to bottom; output order mirrors statement order. That *ordering guarantee* is something we will rely on in every program ahead.

</details>

---

### Chapter 5: The Universal Problem-Solving Process

> **In this chapter you will learn:** the repeatable 7-step process professionals use on almost every programming problem; how to turn vague wishes into precise sentences; how examples expose missing rules; how edge cases prevent 3 a.m. failures; and how the process is applied end-to-end to a real feature. This chapter has almost no code — it is the process you will *follow* in every later chapter.
>
> **Prerequisites:** Chapters 1–4. You should have run at least one program.

#### 5.1 Why a process beats inspiration

Two beginners face the same problem. The first thinks hard, feels a spark, and starts typing. The spark dies somewhere in the middle, tangled in a mess of half-ideas. The second follows a checklist: restate, find examples, hunt edge cases, sketch pseudocode, choose data, build the smallest working version, test and improve. The second one finishes — and — crucially — can do it again tomorrow, and on a deadline, and on a problem ten times bigger.

**The difference is not talent. It is process.** Inspiration is real but unreliable; a process converts problem solving from an event into a *capability*.

#### 5.2 Step 1 — Restate the problem

Turn the vague request into **one precise sentence** (Chapter 1's transformation, now as a deliberate first move). The vaguer the original, the more this step matters.

> Vague: "Make a task app."
>
> Precise v1: "Allow a user to create a task with a non-empty title and display all saved tasks."

Technique: circle every fuzzy word — "app", "task", "display", "saved" — and force each one to mean one thing. If you cannot choose, you have found a **question to ask** (of a client, a teacher, or yourself). Unstated decisions do not disappear; they become bugs later.

#### 5.3 Step 2 — Write concrete examples

Examples are the cheapest bug-finder in existence. A table of 3–5 input → expected output pairs exposes more missing rules than an hour of staring:

| Input | Expected result |
|---|---|
| Title: `Buy milk` | A task is created; success message shown |
| Title: *(empty)* | No task created; an error is shown |
| Title: `"   "` (only spaces) | No task created; an error is shown |
| Three tasks saved | All three appear in the list, newest last |
| No tasks saved | A friendly "no tasks" message — not silence, not a crash |

Notice how example 3 sneaks in a rule nobody mentioned: *is whitespace-only the same as empty?* (We will decide: yes.) Writing examples surfaces exactly these silent decisions while they are still free to make.

#### 5.4 Step 3 — Hunt edge cases

An **edge case** is an input or situation that is unusual, extreme, or hostile — but real. Edge cases are where naive programs die and robust programs are born. Every problem in this guide gets this treatment; here is the standing checklist (you will see it again in Appendix D):

- **Empty** input (empty string, empty list, no file, zero items)
- **Whitespace-only** input (`"   "` pretending to be data)
- **Extreme values** (a number far too large, far too negative, or exactly zero)
- **Exactly one item** (the degenerate-but-valid case; loops written carelessly skip it)
- **Duplicates** (two tasks with the same title — allowed or not?)
- **Wrong type of input** (letters where a number is required)
- **Missing or corrupted external resources** (the save file)
- **Hostile input** (a title 50,000 characters long; characters from other languages; text that looks like a command)
- **Timing** (an operation interrupted halfway; the program killed before saving)

The habit to build: whenever you write a condition or a loop, ask *"what is the smallest, the largest, the empty, and the invalid version of this?"* — and decide, on purpose, what should happen.

#### 5.5 Step 4 — Write the pseudocode

Take the sentence from step 1 and the examples from step 2, and write the solution as structured plain language (Chapter 1.6). For the task manager's menu loop:

```text
load tasks from storage
repeat until the user chooses Exit
    show the menu
    read the user's choice
    if choice is Add
        read and validate the task title
        read the optional description
        read the optional due date
        create the task
        save all tasks
        confirm to the user
    else if choice is List
        display all tasks, or a friendly "no tasks" message
    else if choice is Exit
        stop
    else
        show an unknown-choice message
```

Note the shape: indentation for hierarchy, one action per line, decisions with `if/else`, repetition written as `repeat until`. This *is* the program — C# is just its translation.

#### 5.6 Step 5 — Choose data and operations

Now — and not before — ask the data questions whose full answers arrive in Chapters 10 and 13:

- Is each piece of data **one value** (a title) or **many** (a list of tasks)?
- Must the many keep **order**? (Yes: tasks have IDs and display order.)
- Do I need **fast lookup by key**? (By ID: yes, repeatedly.)
- Can items **change**? (Yes: status changes — so mutable objects fit.)
- Must some states be **impossible by construction**? (Yes: a title that is never empty; a status with only three legal values — exactly what enums and validation give us.)

Choosing data *after* understanding the problem is the order that works. Choosing data first ("let's use a database!") is how projects calcify around wrong structures.

#### 5.7 Step 6 — Implement the smallest working version

Build the **thinnest slice that can actually run**: add one task, list it, nothing else. No search, no persistence, no colors, no menus. Why so tiny?

1. **It reaches reality fastest.** A running skeleton exposes real problems (how input actually behaves, how output actually looks) that no amount of paper can.
2. **Every later feature attaches to something alive.** Adding search to a working program is an afternoon. Adding search to a dream is impossible.
3. **Momentum is a real resource.** A working program at 6 p.m. motivates the next morning.

The anti-pattern this step forbids: building search, cloud sync, notifications, *and* analytics before the basic add-and-list flow works. You will recognize this trap now that it has a name: **horizontal sprawl**. Always grow vertically — one thin working feature at a time.

#### 5.8 Step 7 — Test and improve

Test deliberately, in this order, against the examples from step 2:

1. **Normal cases** — the happy path from the examples table.
2. **Edge cases** — empty, whitespace, one item, duplicates.
3. **Invalid cases** — wrong types, missing file, corrupted file. The program must survive each one and *say something useful*.
4. **Repeated operations** — add ten tasks, delete all, delete one more (which does not exist — what happens?).
5. **Restart behavior** — close, reopen: is the saved state still there? Persistence is the application's long-term memory and the core of Chapters 14 and 16.

Then — only then — improve. **Refactor only when you understand current behavior** (Chapter 19 makes this a safe cycle with tests). Improving without understanding is how working programs are destroyed.

#### 5.9 The process, applied in one page — Worked example

Problem: *"Users should be able to find a task by typing part of its name."*

| Step | Applied |
|---|---|
| 1. Restate | "When the user enters search text, show every task whose title **or** description contains that text, ignoring upper/lower case, ordered by ID." |
| 2. Examples | `c#` finds `Learn C#` (case ignored); `xyz` finds nothing (and says so); empty search text → ask again (it is required); text that matches a **description** word also finds that task |
| 3. Edge cases | Empty text; text longer than any title; spaces around the search word (`"  c# "` should still match); two tasks matching (both shown); no tasks at all |
| 4. Pseudocode | `ask for search text` → `for each task: if title contains text (ignore case) OR description contains text (ignore case), include it` → `show matches or "no tasks found"` |
| 5. Data | We already hold tasks in a list (Chapter 10's `List<TaskItem>`); scanning all of them is correct for hundreds of tasks; per-key index would be premature (Chapter 11) |
| 6. Smallest version | Search titles only, print matches, run it |
| 7. Test & improve | Test `C#` vs `c#` vs `  C# `; add description search; then run the edge list |

This exact feature becomes `TaskManager.Search` in Chapter 17 — with, by then, every C# tool needed to type it. The process is not decoration before "real" programming; **the process is the programming**. The rest is translation.

#### 5.10 Exercises

1. Apply steps 1–2 to a **password checker**: state it in one sentence and write four examples including two edge cases.
2. List five edge cases for a program that reads a number from the user and prints its square.
3. Write pseudocode for a number-guessing game (the computer thinks of a number 1–100; the user guesses until correct; each wrong guess gets "too high" or "too low").
4. What is the *smallest working version* of the guessing game — and which tempting features would you postpone?

<details>
<summary><b>Solutions</b></summary>

**1.** Sentence: "When a user proposes a new password, the program accepts it only if it has at least 8 characters, contains at least one digit, and is not the word 'password' (case-insensitive)." Examples: `h3lloWorld` → accepted; `password1` → rejected (forbidden word); `abc` → rejected (too short); `abcdefgh` → rejected (no digit).

**2.** (a) non-numeric input (`"abc"`); (b) empty input; (c) `0` (square 0 — valid, must not be treated as "nothing"); (d) a huge number whose square overflows the type (e.g. beyond ~2.1 billion for `int` — Chapter 6 explains the limit); (e) negative numbers (square must still be positive — a sign bug is classic).

**3.**

```text
choose a secret number between 1 and 100
repeat until the guess is correct
    ask the user for a guess
    if the guess equals the secret number
        congratulate and stop
    else if the guess is greater than the secret number
        say "too high"
    else
        say "too low"
```

**4.** Smallest version: fixed secret number (say 42), read one guess, print correct/too high/too low, loop. Postpone: random numbers, attempt counting, play-again loops, input validation retries — each is a *next* vertical slice, not part of the first one.

</details>

---

## Part III — The C# Language, One Step at a Time

You can run a program and you own a thinking process. Part III builds your toolbox, one tool per chapter, in strict dependency order — nothing is used before it is taught. Each language chapter follows the same rhythm: **the problem the tool solves → the tool → every line explained → common mistakes → exercises with solutions.**

> **How to run the snippets in Chapters 6–14:** type them into the `Program.cs` of the project you created in Chapter 4 (replacing its content), then `dotnet run`. Predict the output first — every time.

---

### Chapter 6: Variables, Types, and Expressions — Your Program's Memory

> **In this chapter you will learn:** what a variable truly is; how to read a declaration word by word; the built-in types and when to use each (including why money must *never* be `double`); the difference between value types and reference types; `var`; arithmetic, comparison, and logical operators; strings in depth including interpolation; nullable values; and safe type conversion.
>
> **Prerequisites:** Chapters 1–5.

#### 6.1 The problem this chapter solves

A program that cannot *remember* anything can only print fixed text. The moment your program must react — to a user, a file, a calculation — it needs places to store values while it works: the user's age, a list's length, a task's title. A **variable** is that place.

#### 6.2 A variable is a named box in memory

```csharp
int age = 25;
```

Word by word — burn this pattern in, because it appears in nearly every program ever written:

| Piece | Category | Meaning |
|---|---|---|
| `int` | **Type** | "This box holds a whole number" (no decimal point). Choosing the type is choosing the *rules* for the box |
| `age` | **Name (identifier)** | The label we chose. Your name; your rules: letters, digits, `_`; cannot start with a digit; no reserved words; `camelCase` for locals |
| `=` | **Assignment operator** | "Put the value from the right side into the box on the left side." It is *not* mathematical equality — it is an *action* |
| `25` | **Literal** | The value itself, written literally. `25` is an integer literal |
| `;` | Statement terminator | This instruction is complete |

So the whole line says: "reserve memory for a whole number, call it `age`, put `25` in it, done."

Change the value later — assignment again:

```csharp
age = 26;
```

This line does not create anything; it **replaces** the contents of the existing box. The type never changes: once an `int`, always an `int`.

One caution with the word "equals": in C#, `=` is *assignment* (put this in there) and `==` is *comparison* (are these the same?). Mixing them up is a classic bug; Chapter 6.7 makes the distinction permanent.

#### 6.3 The common built-in types

| Type | Example literal | Holds | Use it for |
|---|---|---|---|
| `int` | `42` | Whole numbers, about -2.1 billion to +2.1 billion | Counts, quantities, IDs, indices |
| `long` | `9000000000L` | Whole numbers, about ±9.2 quintillion | Timestamps, huge counts (`L` marks the literal) |
| `double` | `3.14` | Approximate decimal (64-bit floating point) | Science, measurements, graphics — *not* money |
| `decimal` | `19.99m` | Exact base-10 decimal (128-bit) | **Money**, and anything that must round like humans do (`m` for money) |
| `bool` | `true`, `false` | Exactly two states | Decisions: `isAdult`, `isValid`, `hasTicket` |
| `char` | `'A'` | A **single** character (16-bit Unicode) | One letter, digit, or symbol — single quotes |
| `string` | `"hello"` | A sequence of characters | All text — double quotes |
| `DateTime` | `DateTime.UtcNow` | Date + time of day | Timestamps, due dates |
| `DateTime?` | `null` or a date | *Optional* date (nullable — 6.10) | "No due date chosen yet" |

Three of these deserve extra attention.

**`int` has edges.** An `int` holds 32 bits; the largest value is `2,147,483,647`. Overflow silently wraps in unchecked code (`int.MaxValue + 1` becomes a large *negative* number), which is why Chapter 5's edge-case instinct asks: *can this count ever exceed two billion?* If yes, use `long`.

**`double` is approximate.** `double` stores numbers in binary floating point — the standard that powers scientific computing. Its trade: enormous range and speed, but tiny representation error. Run this:

```csharp
double a = 0.1;
double b = 0.2;
Console.WriteLine(a + b);
```

You might predict `0.3` — the actual output is:

```text
0.30000000000000004
```

Not a bug: 0.1 has no exact binary representation, just as 1/3 has no exact decimal one. The error is microscopic — fine for physics, fatal for accounting.

**`decimal` is exact (for base-10).** It stores numbers as decimal digits, so `0.1m + 0.2m` is precisely `0.3m`. Slower, bulkier — and exactly right for money:

```csharp
decimal price = 19.99m;
```

> **Rule: money is `decimal`. Ever.** A bank that loses 0.00000000000000004 cents per transaction is a lawsuit waiting to happen.

#### 6.4 Value types vs reference types — where the box really is

This distinction explains behavior that will otherwise mystify you in about three chapters.

**Value types** (`int`, `long`, `double`, `decimal`, `bool`, `char`, `DateTime`, enums, structs): the variable *is* the box; the value lives directly inside it.

```csharp
int firstNumber = 10;
int secondNumber = firstNumber;   // copies the VALUE
secondNumber = 20;
Console.WriteLine(firstNumber);   // 10 — untouched
Console.WriteLine(secondNumber);  // 20
```

Assignment **photocopies the contents**. Two independent boxes.

**Reference types** (`string`, arrays, `List<T>`, and every `class` you will write): the variable holds a *reference* — an arrow pointing to the object, which lives elsewhere:

```csharp
Person firstPerson = new Person();   // create object; firstPerson POINTS to it
Person secondPerson = firstPerson;   // copies the ARROW
// now both variables point to the ONE same object
```

Change the object through `secondPerson`, and `firstPerson` sees the change too — they are two names for one thing. Diagram:

```text
Value types:      [ firstNumber: 10 ]   [ secondNumber: 20 ]     two boxes

Reference types:  firstPerson ──┐
                              ├──> [ one Person object ]
                  secondPerson ─┘                         one box, two arrows
```

(One comforting exception: `string` behaves *like* a value type in practice — you can never modify a string object through a second variable, because strings are immutable; 6.8.)

#### 6.5 `var` — let the compiler see the type

```csharp
var total = 10 + 5;         // compiler infers: int
var name = "Maya";          // compiler infers: string
```

`var` means: "**you** know what type the right side produces, compiler — use that." It is *not* dynamic typing; `total` is an `int` forever. This line is illegal:

```csharp
var count;
count = 5;      // error: cannot infer — no value at declaration
```

Style guidance: use `var` when the type is obvious from the right side (`var list = new List<int>();`), and the explicit type when the right side does not reveal it. In Part IV you will see both used deliberately.

#### 6.6 Operators — arithmetic

```csharp
int total = 10 + 5;       // 15  addition
int difference = 10 - 5;  // 5   subtraction
int product = 10 * 5;     // 50  multiplication
int quotient = 10 / 5;    // 2   division
int remainder = 10 % 3;   // 1   modulus: remainder after division
```

Every line: type, name, `=`, then an **expression** — a combination of values and operators that *produces* a value. The expression `10 + 5` is evaluated first (to `15`), then assigned.

**The single most important arithmetic fact in C#:** integer division *truncates*:

```csharp
Console.WriteLine(10 / 3);      // 3     — not 3.333
Console.WriteLine(10 % 3);      // 1     — the discarded fraction, as a remainder
Console.WriteLine(10.0 / 3.0);  // 3.3333333333333335 — a double result needs double inputs
```

The `%` operator is your divisibility tool: `n % 2 == 0` means "n is even" (Chapter 1's exercise, now executable). The `10 / 3` behavior also explains a classic bug — averaging three `int` scores as `(a + b + c) / 3` loses the fraction; cast or use `double` deliberately.

Shorthand forms you will read constantly:

```csharp
int count = 10;
count++;        // count = count + 1  → 11  (increment)
count--;        // count = count - 1  → 10  (decrement)
count += 5;     // count = count + 5   → 15
count *= 2;     // count = count * 2   → 30
```

#### 6.7 Operators — comparison and logic

**Comparison operators** produce `bool` values — the fuel for every decision in Chapter 8:

```csharp
int age = 20;
bool isAdult = age >= 18;         // true
bool same = (age == 20);           // true  — == tests equality
bool different = (age != 21);      // true  — != tests inequality
bool younger = age < 18;           // false
bool older = age > 18;             // true
```

The full set: `==` (equal), `!=` (not equal), `<`, `<=`, `>`, `>=`. Read `>=` as "greater than **or** equal." And repeat the oath: *`=` assigns; `==` compares.*

**Logical operators** combine conditions:

```csharp
bool isAdult = true;
bool hasTicket = false;

bool canEnter = isAdult && hasTicket;            // AND: false (both required)
bool needsHelp = !isAdult || hasTicket;          // OR: true  (at least one)
bool isNotEmpty = !string.IsNullOrWhiteSpace(""); // NOT: false (reverses)
```

| `a` | `b` | `a && b` (AND) | `a \|\| b` (OR) | `!a` (NOT) |
|---|---|---|---|---|
| `true` | `true` | `true` | `true` | `false` |
| `true` | `false` | `false` | `true` | `false` |
| `false` | `true` | `false` | `true` | `true` |
| `false` | `false` | `false` | `false` | `true` |

Two professional details:

- **Short-circuiting.** `&&` stops evaluating the moment the answer is certain: in `isAdult && HasTicket()`, if `isAdult` is `false`, `HasTicket()` is never even called. `||` symmetrically stops at the first `true`. This is a *feature* — you can guard calls: `text != null && text.Length > 0` can never crash on `null`.
- **Read conditions aloud.** `age >= 18 && age <= 65` reads as "at least 18 and at most 65." If a condition does not read as a sentence, rewrite it until it does.

#### 6.8 Strings — the most used type

A `string` is a sequence of `char`s. Declaration, length, access:

```csharp
string name = "Maya";
Console.WriteLine(name.Length);   // 4 — Length is a property (data attached to the object)
Console.WriteLine(name[0]);       // M — strings are indexable from 0, like arrays (Chapter 10)
```

**String interpolation** — the `$` prefix — is how modern C# builds text, and it appears in nearly every later chapter:

```csharp
string name = "Maya";
int score = 95;
string message = $"{name} scored {score} points.";
Console.WriteLine(message);        // Maya scored 95 points.
```

Word by word: `$` before the opening quote turns on interpolation — "allow holes"; `{name}` and `{score}` are *holes*: expressions evaluated and converted to text at that position. Everything outside braces is literal. (History note: this C# 6 feature replaced the older `string.Format("...{0}...", name)` style you will still see in old code.)

**The methods you will use most** (every one is called on the string after a `.`):

```csharp
string input = "  Learn C#  ";

string trimmed = input.Trim();                 // "Learn C#"
string lower = input.Trim().ToLowerInvariant();  // "learn c#"
bool startsWithA = "apple".StartsWith("A", StringComparison.OrdinalIgnoreCase); // true
bool containsSharp = input.Contains("C#");     // true
string replaced = input.Replace("C#", "C sharp");      // replace text
```

- `Trim()` — remove leading/trailing whitespace (essential before validating user input — spaces are invisible and everywhere).
- `ToLowerInvariant()` — produce a lowercase copy for case-insensitive comparisons. Why not `ToLower()`? "Invariant" ignores the current country settings of the machine — the Turkish locale famously maps capital `I` to `ı`, which corrupts naive lowercasing. Invariant is *safe everywhere*.
- The `StringComparison.OrdinalIgnoreCase` overloads ask "does it start with A, ignoring case?" without creating copies — the professional form, used in Chapter 17's search.

**Immutability.** Strings can never be modified after creation — every "modifying" method returns a *new* string and leaves the original untouched:

```csharp
string original = "task";
string upper = original.ToUpperInvariant();
Console.WriteLine(original);   // task — unchanged!
Console.WriteLine(upper);       // TASK
```

So this classic beginner bug does nothing:

```csharp
string title = "task";
title.ToUpperInvariant();      // creates TASK... and throws it away
Console.WriteLine(title);      // task — the bug: forgot to capture the result
```

Correct: `title = title.ToUpperInvariant();`

**Empty and whitespace.** `" "` (a space) is not empty, yet rarely valid input:

```csharp
bool isNothing = string.IsNullOrEmpty("");     // true for "" or null
bool isEffectivelyNothing = string.IsNullOrWhiteSpace("   ");  // true even for spaces
```

`IsNullOrWhiteSpace` is the single most useful input-check in this entire guide; it guards every required input from Chapter 7 onward.

#### 6.9 Formatting values inside interpolation

Interpolation holes can include format instructions after a `:` — used constantly with dates and numbers (full details of dates in 6.10 and Chapter 14):

```csharp
double price = 1234.5678;
Console.WriteLine($"{price:F2}");                 // 1234.57   — fixed 2 decimals
Console.WriteLine($"{1234567:N0}");               // 1,234,567 — thousands separators

DateTime now = DateTime.UtcNow;
Console.WriteLine($"{now:yyyy-MM-dd}");           // 2026-11-09 — year-month-day
Console.WriteLine($"{now:yyyy-MM-dd HH:mm}");    // 2026-11-09 14:30 — with time
```

Meaning of the letters: `yyyy` 4-digit year, `MM` two-digit month (**capital** — lowercase `mm` is minutes), `dd` two-digit day, `HH` 24-hour hour, `mm` minutes. `F2` = "fixed, 2 fraction digits"; `N0` = "number, 0 fraction digits, with separators." The `yyyy-MM-dd` pattern (biggest unit first) sorts alphabetically into correct chronological order — which is why it is *the* recommended date format for files and logs.

#### 6.10 Nullable value types — "no value" as a value

Real problems contain absence: a task with *no due date yet*; an answer that is *not given*. For value types, C# expresses absence with `?`:

```csharp
DateTime? dueDate = null;      // dueDate holds either a real date OR "no date"
```

Read `DateTime?` as "optional DateTime." You cannot use it as if it were definitely a date:

```csharp
DateTime? dueDate = null;
Console.WriteLine(dueDate.Value);   // crash: InvalidOperationException — nothing is inside
```

Check first — the two professional patterns:

```csharp
if (dueDate.HasValue)
{
    Console.WriteLine(dueDate.Value.ToString("yyyy-MM-dd"));  // .Value unwraps the date
}
```

or pattern matching, the more modern form you will see throughout Part IV:

```csharp
if (dueDate is DateTime actualDate)   // "if it IS a date, capture it as actualDate"
{
    Console.WriteLine(actualDate.ToString("yyyy-MM-dd"));
}
```

And the two related operators you will meet in every file of Part IV:

- `?.` — null-conditional: `text?.Trim()` means "trim it, but if `text` is null the result is just null — don't crash."
- `??` — null-coalescing: `text ?? ""` means "use `text`, but if it is null, use `""` instead."

Combined (ubiquitous from Chapter 7): `Console.ReadLine()?.Trim() ?? ""` — "read a line; trim it if possible; if everything failed, use empty text."

#### 6.11 Converting between types

**Widening is automatic** (small → big never loses data):

```csharp
int number = 42;
double wide = number;      // int → double: automatic
```

**Narrowing requires a cast** — an explicit "I know what I am doing":

```csharp
double pi = 3.99;
int truncated = (int)pi;    // 3 — cast; the fraction is DISCARDED (not rounded)
```

**Text to number is where beginners live**, and C# has a deliberate split:

```csharp
// Parse: converts, but CRASHES (throws) on bad input
int value = int.Parse("42");        // works
int broken = int.Parse("abc");      // crashes with FormatException — the program dies

// TryParse: converts WITHOUT ever crashing — returns success/failure
if (int.TryParse("42", out int result))
{
    Console.WriteLine(result);      // 42
}
if (int.TryParse("abc", out int other))
{
    // never reached — TryParse returned false
}
```

`TryParse`'s anatomy, word by word:

- `int.TryParse(...)` — a method on the `int` type that *attempts* a conversion.
- First argument: the text to try.
- `out int result` — an **output parameter**: the method *writes* its answer into this variable when it succeeds. `out` marks a variable as "filled in by the method."
- Return value: `bool` — `true` means "conversion worked, and `result` now holds the number"; `false` means "it failed, ignore `result`."

> **Rule: for user input, always `TryParse`.** `Parse` on user input is a program waiting to die (Chapter 7 makes this the law; `DateTime.TryParse` follows the identical pattern).

#### 6.12 Common beginner mistakes (recognize these forever)

| Wrong | Why it hurts | Right |
|---|---|---|
| `if (age = 18)` | Assigns 18 instead of comparing; `int` is not a condition → compile error | `if (age == 18)` |
| `double money = 19.99;` | Binary rounding: cents drift in accounting | `decimal money = 19.99m;` |
| `title.ToUpper();` alone | Result discarded (strings immutable) | `title = title.ToUpper();` |
| `int half = 5 / 2;` | Integer division: `2`, silently | `double half = 5 / 2.0;` → `2.5` |
| `string d = "5"; int n = d.Length;` etc. | Confusing the string with its meaning | Convert explicitly with `TryParse` |
| `DateTime d = null;` | `DateTime` cannot be null | `DateTime? d = null;` |

#### 6.13 Exercises

1. Write a program that declares variables for a rectangle's width and height, then prints its area and perimeter with `Console.WriteLine` and interpolation.
2. Write a Celsius → Fahrenheit converter: `F = C × 9/5 + 32`. Test with `0`, `100`, `37`. (Careful with 6.6!)
3. Read a number into an `int` variable and print whether it is positive, negative, or zero.
4. Build a full name from `firstName`, `lastName`, and a `title` using one interpolated string.
5. Explain, in your own words, why money must use `decimal`, in two sentences a manager would understand.
6. Predict, then run:

```csharp
int a = 7, b = 2;
Console.WriteLine($"{a} / {b} = {a / b}");
Console.WriteLine($"{a} % {b} = {a % b}");
double da = 7, db = 2;
Console.WriteLine($"{da} / {db} = {da / db}");
```

<details>
<summary><b>Solutions</b></summary>

**1.**

```csharp
double width = 4.5;
double height = 2.0;
double area = width * height;
double perimeter = 2 * (width + height);
Console.WriteLine($"Area: {area}, perimeter: {perimeter}");
// Area: 9, perimeter: 13
```

**2.**

```csharp
double celsius = 37.0;
double fahrenheit = celsius * 9 / 5 + 32;   // 9/5 would be fine here: celsius*9 happens first
Console.WriteLine($"{celsius}°C = {fahrenheit}°F");
// 0 → 32, 100 → 212, 37 → 98.6
```

Note: `celsius * 9 / 5` is `(celsius * 9) / 5` — left to right for equal precedence — and since `celsius` is `double`, every step stays `double`. Had we written `9 / 5 * celsius`, the integer `9 / 5` would have truncated to `1` *first* and every answer would be wrong — operators of equal precedence evaluate left to right.

**3.**

```csharp
int number = -5;
if (number > 0) Console.WriteLine("positive");
else if (number < 0) Console.WriteLine("negative");
else Console.WriteLine("zero");
// negative
```

(Yes — this uses `if`/`else` one chapter early; it is included because "positive/negative/zero" is the natural test for variables, and a taste of Chapter 8.)

**4.**

```csharp
string firstName = "Maya";
string lastName = "Haddad";
string title = "Ms.";
Console.WriteLine($"{title} {firstName} {lastName}");
// Ms. Maya Haddad
```

**5.** "Computers store everyday decimals like 0.10 in binary, which cannot represent them exactly — so repeated additions drift by tiny fractions, and accounts must never drift. The `decimal` type stores numbers the way people do, digit by digit, so money always adds up."

**6. Predicted output (verify):**

```text
7 / 2 = 3
7 % 2 = 1
7 / 2 = 3.5
```

First line: integer division truncates. Second: the remainder proves why. Third: `double` inputs → genuine division.

</details>

---

### Chapter 7: Input, Output, and Validation — Talking to the User

> **In this chapter you will learn:** how to read text from the terminal; why user input is the most dangerous stream of data in your program; how to validate it; the full anatomy of `TryParse`; and how to build reusable, safe input helpers — including one 11-line method explained line by line that will be reused, unchanged, in the real application of Part IV.
>
> **Prerequisites:** Chapter 6.

#### 7.1 The problem this chapter solves

Every program with users has a trust boundary: the line where data you do not control enters your world. Everything before the line is your logic (predictable, tested); everything crossing the line is *their* input — and users type the darndest things. This chapter is about surviving that boundary with grace. It is the difference between a demo and an application.

#### 7.2 The three console verbs

Everything a console program can do with a human, in three methods:

```csharp
Console.Write("Enter your name: ");     // print WITHOUT newline (prompt stays on the line)
string? name = Console.ReadLine();       // read ONE line the user types; can be null!
Console.WriteLine($"Hello, {name}!");    // print WITH newline
```

Word by word:

- `Console.Write(prompt)` — prints and leaves the cursor on the same line, so the user's typing appears next to the question. That is why prompts use `Write`, not `WriteLine`.
- `Console.ReadLine()` — waits (the program truly stops) until the user presses Enter, then returns everything they typed **as a string**, *without* the Enter key itself. It can return `null` — end-of-input, for example when input is piped from a file and ends (Chapter 5's "hostile situation" list, in real life).
- `string?` — the nullable annotation from 6.10: "this variable may hold no string at all." The compiler now *forces* us to handle that possibility — which is the point of nullable annotations: turning "might crash someday" into "must be handled now."

A complete interaction program:

```csharp
Console.Write("Enter your name: ");
string? name = Console.ReadLine();
Console.WriteLine($"Hello, {name}!");
```

Sample run:

```text
Enter your name: Maya
Hello, Maya!
```

#### 7.3 Why you must never trust input

Users — accidentally or deliberately — will send you:

- **nothing** (they press Enter immediately → empty string);
- **spaces** (`"   "` — looks empty to the eye, is not empty to the machine);
- **the wrong type** (`"abc"` where you asked for an age);
- **out-of-range values** (`-5`, `9999`, `20000000000000`);
- **unexpected commands** (they type `q` when your menu only knows `1`–`5`).

**Validation** is the discipline of checking input against the rules *before* using it. The five-part table from Chapter 1 returns: the *rules* column is exactly what we now enforce. A rule you never wrote cannot be enforced — which is why the thinking chapters came first.

#### 7.4 The law for numbers: `TryParse`, never `Parse`

The rule from 6.11, now applied to real users. Ask for an age and *survive* whatever comes back:

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

Line by line:

1. `Console.Write("Enter your age: ")` — the prompt, no newline.
2. `string? text = Console.ReadLine();` — read the raw text; may be null; we deliberately keep it as a string and *never* assume.
3. `int.TryParse(text, out int age)` — attempt conversion; `true` only if `text` is a genuine whole number; on success `age` now holds the number (the `out` parameter, 6.11).
4. `&& age >= 0 && age <= 130` — short-circuiting (6.7) is *load-bearing* here: if the parse failed, `age` is meaningless, and `&&` guarantees the range checks are never evaluated against it. One condition, safely ordered.
5. The `if` body runs only when everything held: valid number *and* sane range.
6. The `else` catches **all** other cases — unparseable text, null, `"-3"`, `"1400"`. One message, no crash.

Sample runs:

```text
Enter your age: 34
Your age is 34.

Enter your age: thirty-four
Please enter an age from 0 to 130.

Enter your age: -3
Please enter an age from 0 to 130.
```

#### 7.5 A reusable helper — required text

Professional programs do not copy-paste validation; they *name* it. Here is a method (full anatomy of methods in Chapter 9 — for now, read it as "a named block of behavior we can call repeatedly") that demands a non-empty answer, forever, until the user provides one:

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

And the promised line-by-line — all 11 statements:

1. **`static string ReadRequiredText(string prompt)`** — the *header*: `static` means it belongs to the class, not to an object (explained fully in Chapter 9); `string` before the name is the **return type** — this method hands back text; `ReadRequiredText` — the chosen name, verb-first, self-documenting; `(string prompt)` — one **parameter**: a value the caller provides, here the question to display.
2. **`while (true)`** — an intentional *infinite* loop (Chapter 8 teaches loops properly). "Repeat the block below forever" — with the only exits being the `return` inside.
3. **`Console.Write(prompt);`** — show the caller's question, no newline.
4. **`Console.ReadLine()?.Trim() ?? ""`** — the densest line in this chapter, operator by operator: `ReadLine()` gives `string?` → `?.Trim()` trims surrounding whitespace *if* the input was not null (and yields null if it was) → `?? ""` replaces any surviving null with the empty string. **Net effect: `value` is always a real string — never null — no matter what the input stream did.** Defensive programming in one line.
5. **`if (!string.IsNullOrWhiteSpace(value))`** — the validation itself, using the workhorse from 6.8: is the text *anything more* than whitespace? The `!` reverses it: "if the text has real content…"
6. **`return value;`** — the first exit: hand the cleaned, validated text back to whoever called us. The loop ends because `return` leaves the method entirely.
7. **`Console.WriteLine("A value is required.");`** — reached only when validation failed: explain, and… the loop repeats: back to line 3 automatically. The user is asked again.

Call it — three lines instead of a validation block each time:

```csharp
string title = ReadRequiredText("Title: ");
Console.WriteLine($"You entered: {title}");
```

Sample run (watch it refuse and re-ask):

```text
Title:
A value is required.
Title:    Buy milk
A value is required.
Title: Buy milk
You entered: Buy milk
```

(The second attempt looked typed but was spaces — `Trim` + `IsNullOrWhiteSpace` caught the invisible lie.)

This exact method ships in the application of Part IV (as `InputReader.ReadRequiredText`, Chapter 18) — you are already reading production code.

#### 7.6 The validation mindset — a summary you can reuse forever

For every input that crosses your boundary, ask, in order:

1. **Is it present?** (not null, not empty, not whitespace)
2. **Is it the right type?** (`TryParse`)
3. **Is it the right range?** (0–130; a positive ID; a date not in the past)
4. **Is it the right shape?** (length limits; allowed characters; valid menu choices)
5. **Is it safe to use?** (never executed as a command; never trusted with security decisions)

Only after all five answers are yes does input become *data* — trusted, clean, usable. Before that, it is just noise attempting to become a bug.

#### 7.7 Exercises

1. Write a program that asks for the user's favorite number and survives `abc`, an empty answer, and `99999999999999999999` (too big for `long`? test it!).
2. Write `ReadIntInRange(int min, int max)` — keeps asking until it gets a whole number within `[min, max]`.
3. Why is the order of the condition in 7.4 (`TryParse(...) && range checks`) essential? What would break if reversed, and what would the symptom be?
4. A password rule demands 8+ characters, one digit, one letter. Write the validation as an `if` using `&&`, `||`, `string` methods — no loops.

<details>
<summary><b>Solutions</b></summary>

**1.** Reuse the 7.4 pattern; the giant number fails `TryParse` (out of `long` range → returns `false`, no crash). The lesson: `TryParse` refuses *politely* instead of exploding — the exact behavior that makes it the law.

```csharp
Console.Write("Favorite number: ");
if (long.TryParse(Console.ReadLine(), out long n))
{
    Console.WriteLine($"Got it: {n}");
}
else
{
    Console.WriteLine("That is not a number I can hold.");
}
```

**2.**

```csharp
static int ReadIntInRange(int min, int max)
{
    while (true)
    {
        Console.Write($"Enter a number {min}-{max}: ");
        if (int.TryParse(Console.ReadLine(), out int value) && value >= min && value <= max)
        {
            return value;
        }
        Console.WriteLine($"Please enter a whole number between {min} and {max}.");
    }
}
```

**3.** If reversed, the range check would run *before* the parse — comparing a garbage value from an unassigned/failed parse, and (without short-circuiting) `TryParse`'s `out` value is meaningless on failure. With `&&`, the left-to-right, short-circuiting evaluation guarantees: parse first, range-check only real numbers. Symptom if reversed: misleading range errors like "enter 0–130" for input `"abc"`, or worse, accepting garbage that happens to fall in range.

**4.**

```csharp
string password = "h3lloWorld";
bool lengthOk = password.Length >= 8;
bool hasDigit = password.Any(char.IsDigit);
bool hasLetter = password.Any(char.IsLetter);
bool valid = lengthOk && hasDigit && hasLetter;
Console.WriteLine(valid ? "accepted" : "rejected");
```

(`Any` is a taste of LINQ, Chapter 10: "is there at least one character that is a digit?")

</details>

---

### Chapter 8: Decisions and Repetition — Teaching the Program to Choose and Repeat

> **In this chapter you will learn:** `if` / `else if` / `else` in full; the `switch` statement; all four C# loops (`while`, `do`-`while`, `for`, `foreach`) with their exact anatomy; `break` and `continue`; how to trace a loop by hand; the two classic loop bugs (infinite loops and off-by-one); and a decision table for choosing the right loop.
>
> **Prerequisites:** Chapters 6–7.

#### 8.1 The problem this chapter solves

So far every program has been a straight line: statement, statement, statement, end. Real problems are not lines — they are *"if the title is empty, refuse; otherwise, save"* (choice), and *"check every task; list every task; retry until valid"* (repetition). Choice and repetition are the only two forms of control flow a program needs — with them, everything from a calculator to an operating system is expressible.

#### 8.2 `if` — the fork in the road

```csharp
int temperature = 35;

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

Anatomy, word by word:

- `if` — keyword: "I am about to make a decision."
- `(temperature > 30)` — the **condition**, always inside parentheses, always producing a `bool` (Chapter 6.7's operators are the fuel).
- `{ ... }` — the **body**: statements to run *only if* the condition was true. The braces mark where the "if-territory" begins and ends.
- `else if (...)` — checked only when every earlier condition was false. Chain as many as you need; they are tested top to bottom, and **only the first true branch runs**.
- `else` — the fallback: runs when everything above was false. Optional, but a professional habit: a decision without an `else` is a decision whose "otherwise" you have not thought about.

Execution of the example, statement by statement: `35 > 30` → true → print "It is hot." → **the whole chain is done**; the `else if` and `else` are never even evaluated. The flow:

```text
            temperature > 30 ?
           ┌──── yes ────┐        ┌──── no ──────┐
           │ print "hot" │        │ temperature < 10 ?
           └─────────────┘        │  yes → "cold"     no → "moderate"
                                  └───────────────────────────
```

One rule the compiler enforces for you: the condition must be a `bool`. `if (temperature)` is illegal C# (unlike C's historical truthiness); you must write `if (temperature > 30)`. You will thank this rule every time it catches a half-finished thought.

#### 8.3 `switch` — one value, many known cases

When a *single* value is compared against several exact alternatives, `switch` says it more clearly than an `if` chain:

```csharp
string choice = "2";

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

Word by word:

- `switch (choice)` — "compare this one value against the cases below."
- `case "1":` — "if the value equals `"1"`, start here."
- `break;` — **mandatory** in C#: "leave the switch now." Without it, the compiler errors (CS016 "unreachable code" family) — C# deliberately refuses the accidental fall-through that made C bugs famous.
- `default:` — "if nothing matched" — the switch's `else`. Always write it for user-driven values; the unknown *always* arrives.

Choose between them: **`if` for ranges and complex conditions** (`temp > 30`), **`switch` for one value with discrete known options** (menu choices, status codes, enum values — the enum case arrives in Chapter 15). Both are correct tools; readability decides.

#### 8.4 `while` — repeat while a condition holds

```csharp
int count = 1;

while (count <= 3)
{
    Console.WriteLine(count);
    count++;
}
```

Output:

```text
1
2
3
```

Anatomy: `while (condition) { body }` — check the condition; if true, run the body; check again; repeat until the condition is false, then continue *after* the loop.

The body must eventually make the condition false — here `count++` (Chapter 6.6's increment) pushes `count` past 3. **The three essential pieces of every count-controlled loop** exist in this example: initialize before (`count = 1`), test at the top (`count <= 3`), advance inside (`count++`). Lose any one and the loop misbehaves — most spectacularly the third:

```csharp
// the classic infinite loop — read it, recognize it, never ship it
int n = 1;
while (n <= 3)
{
    Console.WriteLine(n);
    // forgot n++ — condition never becomes false — Ctrl+C to escape
}
```

The program prints `1` forever. The condition *can* never change because nothing in the body changes the variables it reads. When a program "hangs," this is what it is doing — and now you know to look for the missing advance.

#### 8.5 `do`-`while` — repeat *until*, asking at least once

```csharp
string answer;

do
{
    Console.Write("Continue? (y/n): ");
    answer = Console.ReadLine()?.Trim().ToLowerInvariant() ?? "";
}
while (answer == "y");
```

The one difference from `while`: a `do`-`while` **runs the body first, tests after** — guaranteeing at least one execution. Perfect for "ask the user, then decide whether to ask again" flows, where asking must happen at least once. Note the `;` after the condition — the syntax demands it.

#### 8.6 `for` — the counting loop, preassembled

When you know the shape is "count from here to there," `for` puts all three essential pieces on one line where none can be forgotten:

```csharp
for (int index = 0; index < 5; index++)
{
    Console.WriteLine(index);
}
```

Output:

```text
0
1
2
3
4
```

The three slots, separated by semicolons inside the parentheses:

| Slot | Code here | Runs when |
|---|---|---|
| 1. **Initializer** | `int index = 0` | Once, before the loop starts |
| 2. **Condition** | `index < 5` | Before *every* iteration, including the first — stop when false |
| 3. **Update** | `index++` | After *every* iteration, before the next test |

Execution trace of the whole loop:

| Iteration | `index` at test | `index < 5`? | Body prints | Update |
|---|---|---|---|---|
| 1 | 0 | true | `0` | → 1 |
| 2 | 1 | true | `1` | → 2 |
| 3 | 2 | true | `2` | → 3 |
| 4 | 3 | true | `3` | → 4 |
| 5 | 4 | true | `4` | → 5 |
| — | 5 | **false** | loop ends | |

Two deliberate details in that trace:

- **It starts at 0 and uses `<`, not `<=`** — so it runs exactly `5` times for the numbers `0..4`. Starting at zero is not a quirk; it is how arrays index (Chapter 10), and `"start at 0, keep while < count"` is the pattern that accesses *exactly* every element with no extras.
- **`int index` is declared inside the `for`** — it exists only within the loop (Chapter 9 formalizes *scope*). Two `for` loops may each declare their own `index` without colliding.

#### 8.7 `foreach` — visit every item, no counting

When you have a collection of items and want *each* of them, you do not need an index at all:

```csharp
string[] names = { "Ari", "Bo", "Cy" };   // an array of three strings (arrays: Chapter 10)

foreach (string name in names)
{
    Console.WriteLine(name);
}
```

Output:

```text
Ari
Bo
Cy
```

Word by word: `foreach` — "for every element"; `(string name in names)` — "take the collection `names`; for each item in it, call it `name` (a fresh copy each iteration)"; body runs once per item, in order, first to last.

`foreach` vs `for`: `foreach` when you *use* each item and do not need positions — it is shorter and cannot miscount; `for` when you genuinely need the index (positions, mathematical relationships, or modifying the collection's structure while iterating).

#### 8.8 `break` and `continue` — early exits

Two keywords refine loops:

```csharp
// break: stop the ENTIRE loop right now — e.g. "found it, stop searching"
foreach (string name in names)
{
    if (name == "Bo")
    {
        Console.WriteLine("Found Bo.");
        break;                 // remaining items never visited
    }
}

// continue: skip the REST of THIS iteration, jump to the next one
for (int i = 0; i < 5; i++)
{
    if (i % 2 == 0)
    {
        continue;              // skip even numbers entirely
    }
    Console.WriteLine(i);      // prints 1 and 3 only
}
```

Use them *sparingly and deliberately* — each is a small jump in the flow of reading. Professional rule of thumb: one `break` as a clear "found it / stop" is excellent; five scattered `continue`s in a nested forest is unreadable.

#### 8.9 Nested loops — a loop inside a loop

```csharp
for (int row = 1; row <= 3; row++)
{
    for (int col = 1; col <= 3; col++)
    {
        Console.Write($"({row},{col}) ");
    }
    Console.WriteLine();      // after each row: newline
}
```

Output:

```text
(1,1) (1,2) (1,3)
(2,1) (2,2) (2,3)
(3,1) (3,2) (3,3)
```

Execution rule: **for every single iteration of the outer loop, the inner loop runs completely.** 3 outer × 3 inner = 9 total body executions. The `row` variable moves once per *line*; the `col` variable races within each line. Nested loops multiply: if both loops run `n` times, the body runs `n × n` times — remember this when Chapter 11 introduces **O(n²)** — it is exactly this shape.

#### 8.10 The two classic loop bugs

1. **The infinite loop** (8.4): the condition can never become false because the body never changes what the condition reads. Symptom: the program hangs. Fix: find the variable the condition depends on and advance it.
2. **The off-by-one error (OBOE)**: starting at 1 with `<` (or 0 with `<=`) — running one time too many or too few, or reading one element past the end:

```csharp
int[] scores = { 90, 75, 88 };        // exactly 3 elements: indexes 0, 1, 2
for (int i = 0; i <= 3; i++)           // BUG: <= 3 tries index 3 — which does not exist
{
    Console.WriteLine(scores[i]);      // crash at i == 3: IndexOutOfRangeException
}
```

Correct: `i < 3` (or `scores.Length`, Chapter 10). The invariant to internalize: **valid indexes run from `0` to `length - 1`** — the last valid index is *always* one less than the count. Half of all beginner array bugs live in that single sentence.

#### 8.11 Choosing the right loop — decision table

| Situation | Loop to reach for | Why |
|---|---|---|
| Repeat until some condition changes; unknown count in advance | `while` | Tests first — may legally run zero times |
| Must run at least once (ask, then decide) | `do`-`while` | Body-before-test guarantees the first execution |
| Known counting pattern (indices, `n` times) | `for` | All three pieces on one line; nothing forgotten |
| Have a collection, want each item | `foreach` | No index bookkeeping; cannot OBOE |
| Search a collection for a match | `foreach` + `break` | "Stop at the first hit" is the clearest form |

#### 8.12 Exercises

1. Print the numbers 1–10 with a `while`, then again with a `for`.
2. Print the even numbers 2–20.
3. Print this triangle (5 rows) with nested loops:
   ```text
   *
   **
   ***
   ****
   *****
   ```
4. FizzBuzz (the classic): print 1–100, but multiples of 3 print `Fizz`, multiples of 5 print `Buzz`, multiples of both print `FizzBuzz`.
5. Ask the user for numbers until they type `done`, then print the largest — validation included (7.4 pattern).

<details>
<summary><b>Solutions</b></summary>

**1.**

```csharp
int n = 1;
while (n <= 10) { Console.WriteLine(n); n++; }

for (int i = 1; i <= 10; i++) { Console.WriteLine(i); }
```

**2.**

```csharp
for (int i = 2; i <= 20; i += 2)     // start 2, step 2: 2,4,6,...,20
{
    Console.WriteLine(i);
}
```

**3.**

```csharp
for (int row = 1; row <= 5; row++)
{
    for (int star = 0; star < row; star++)
    {
        Console.Write("*");
    }
    Console.WriteLine();
}
```

Row 1 prints 1 star (inner runs once), row 2 twice, … row 5 five times.

**4.**

```csharp
for (int i = 1; i <= 100; i++)
{
    if (i % 15 == 0)     Console.WriteLine("FizzBuzz");   // 15 = 3×5: test FIRST
    else if (i % 3 == 0) Console.WriteLine("Fizz");
    else if (i % 5 == 0) Console.WriteLine("Buzz");
    else                 Console.WriteLine(i);
}
```

The order is the lesson: the *combined* condition must be tested before the singles, or 15 prints "Fizz" and never reaches "FizzBuzz".

**5.**

```csharp
int largest = int.MinValue;     // smaller than any number the user can type
bool anyNumber = false;

while (true)
{
    Console.Write("Number (or 'done'): ");
    string input = Console.ReadLine()?.Trim() ?? "";

    if (input == "done")
    {
        break;
    }
    if (int.TryParse(input, out int value))
    {
        anyNumber = true;
        if (value > largest)
        {
            largest = value;    // a new champion
        }
    }
    else
    {
        Console.WriteLine("Not a number — try again.");
    }
}

if (anyNumber) Console.WriteLine($"Largest: {largest}");
else            Console.WriteLine("No numbers entered.");
```

This tiny program uses everything: infinite loop + `break`, validation, a running maximum, and an edge case ("no numbers at all") handled deliberately. It is Chapter 1's largest-number algorithm, alive.

</details>

---

### Chapter 9: Methods — Naming Your Solutions

> **In this chapter you will learn:** why methods are the most important structural tool in programming; the complete anatomy of a method, word by word; parameters vs arguments; `void` and `return`; expression-bodied methods; scope; overloading; the design rules of a good method; guard clauses; and a worked decomposition — turning a 40-line blob into five clean methods, which is the exact mental move Part IV performs on the whole application.
>
> **Prerequisites:** Chapters 6–8.

#### 9.1 The problem this chapter solves

Copy this loop, paste it five times, adjust five numbers, and fix the same bug in five places — forever. That is life without methods. A **method** is a named block of behavior: write it once, call it by name anywhere, test it alone, and fix it once. Methods are how humans scale programs past what a mind can hold — and, more deeply, they are how you *name solutions*.

There is a second, subtler power: a method forces you to give a behavior a *name*, and a good name forces you to *understand* the behavior. `ValidateTitle` cannot be written until you know what makes a title valid. Naming is understanding.

#### 9.2 Anatomy of a method — word by word

```csharp
static int Add(int left, int right)
{
    return left + right;
}
```

| Piece | Word | Meaning |
|---|---|---|
| `static` | **Modifier** | "Belongs to the class itself, not to one object" — for now: callable directly from top-level code / `Main`. (The full meaning arrives with objects, Chapter 13.) |
| `int` | **Return type** | "When this method finishes, it hands back an `int`." The compiler will *enforce* this promise |
| `Add` | **Name** | You choose; verb-first (`Add`, `Find`, `Print`), `PascalCase` |
| `(int left, int right)` | **Parameter list** | The inputs the method needs, each with a type and a name. Zero to many, comma-separated |
| `{ ... }` | **Body** | The statements that run, top to bottom, when the method is called |
| `return left + right;` | **Return statement** | Compute the expression, hand the result to the caller, and **end the method immediately** |

Calling it — and the vocabulary distinction to memorize:

```csharp
int result = Add(2, 3);        // the values 2 and 3 are ARGUMENTS
```

- **Parameter** = the declared placeholder in the method (`int left`).
- **Argument** = the actual value you pass in the call (`2`).

Arguments fill parameters, positionally: `left` receives `2`, `right` receives `3`. Execution at the call site: jump into `Add` with the values in place → run the body → `return` carries `5` back → the call site expression `Add(2, 3)` *becomes* `5` → assigned to `result`. A call is an expression that produces the return type's value — you can nest them: `Add(Add(1, 2), Add(3, 4))` is `Add(3, 7)` is `10`.

#### 9.3 `void` — when there is nothing to hand back

```csharp
static void ShowWelcome()
{
    Console.WriteLine("Welcome!");
}
```

`void` means "this method performs an action and returns *nothing*." Call it for its effect, not for a value:

```csharp
ShowWelcome();        // no assignment — there is nothing to assign
```

An empty parameter list `()` means "I need nothing from you."

Return-early pattern — one of the most useful shapes in daily code (it returns the *first* problem found and stops):

```csharp
static string FirstProblem(int age)
{
    if (age < 0)
    {
        return "Age cannot be negative.";     // exit immediately with this answer
    }
    if (age > 130)
    {
        return "Age looks unrealistic.";
    }
    return "No problems found.";             // the "all clear" path
}
```

Note how each `return` ends the method — later lines never run for a given input. The compiler enforces one law: a non-`void` method must return on **every** possible path. Forget a path and you get `CS0161: not all code paths return a value` — the compiler proving it enumerated your branches better than you did.

#### 9.4 Expression-bodied methods — small method, one line

When the body is a single `return expression;`, C# offers the compact form you will see everywhere:

```csharp
static int Add(int left, int right) => left + right;

static double CelsiusToFahrenheit(double celsius) => celsius * 9 / 5 + 32;
```

Read `=>` as "returns the value of". Same behavior, no ceremony; ideal for one-line formulas.

#### 9.5 Scope — where names live

**Scope** = the region of code where a name is usable. The braces `{ }` are its fences:

```csharp
static void Example()
{
    int localValue = 10;          // born here...
    Console.WriteLine(localValue); // ...used here: fine
}
// ...dead here: the method's locals vanish when it returns

static void Other()
{
    Console.WriteLine(localValue); // compile error: name 'localValue' does not exist
}
```

Rules that matter daily:

- **Locals** (declared inside a method) live only inside it, and only from declaration to the closing brace.
- **Parameters** behave like locals pre-filled by arguments.
- Each `for` loop's `int i` (8.6) is scoped to that loop — two loops may reuse the same name.
- **Fields** — variables declared at the *class* level (Chapter 13) — live as long as the object does, visible to every method of the class. Part IV uses this everywhere.

Scope is a *feature*, not a bother: things that vanish cannot collide, and names that exist everywhere get tangled.

#### 9.6 Overloading — same idea, different signatures

Two methods may share a name if their parameter lists differ — the **signature** is the combination of name + parameter types:

```csharp
static void Print(int value)    => Console.WriteLine($"Number: {value}");
static void Print(string value) => Console.WriteLine($"Text: {value}");

Print(42);        // calls the int version
Print("hi");      // calls the string version
```

The compiler picks by matching argument types. This is how one name stays consistent across variations (the .NET library does it constantly — e.g., `Console.WriteLine` has 18 overloads for every printable type). Use it when the *behavior* is genuinely the same idea; abuse it when the behaviors differ, and you get confusion instead of clarity.

#### 9.7 The design rules of a good method

Five rules, each with its why:

1. **One responsibility.** A method does one thing, at one level of detail. `AddTask` adds a task. It does not also print the menu.
2. **A meaningful, verb-first name.** If you cannot name it, you have not understood it.
3. **Takes what it needs as parameters; returns what it produced.** Not globals, not magic — the inputs and outputs are *visible in the signature*, which makes the method testable (12.5) and reusable.
4. **No secret side effects.** It does not quietly modify distant state or print when the name says "Calculate". Side effects belong in the name (`PrintReport`) or not at all.
5. **Short enough to hold in your head.** A common professional guideline is "fits on one screen"; the real test is "each paragraph of it has a single reason to change."

The classic bad names — feel the contrast:

```csharp
DoIt();                       // bad: does WHAT?
HandleStuff(bool flag);       // bad: what stuff? what flag?
ValidateTaskTitle();          // good: a promise you can hold it to
CalculateTotal();             // good
DisplayTaskList();            // good
```

#### 9.8 Guard clauses — fail fast at the door

A **guard clause** is an early `if` that rejects invalid input immediately, letting the *main* logic below stay un-indented and honest:

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

    return price * percentage / 100m;      // the actual logic: 1 line, unburied
}
```

Read it top to bottom as a conversation: "A negative price? — invalid, here is an exception. A percentage outside 0–100? — invalid, exception. Now that *everything below is guaranteed sane*, the real formula fits on one un-indented line."

Three details:

- `throw new ...Exception(...)` — the method *refuses*: it raises an exceptional failure (Chapter 14 owns exceptions; for now: "blow up loudly with a message"). This is for **programmer** errors — broken invariants, misuse — as opposed to *user* errors, which should be met with a re-asking loop, never an exception (Chapter 7's `ReadRequiredText` vs this distinction: users get politeness, programmers get exceptions).
- `nameof(price)` — the `nameof` operator (C# 6) produces the *text* `"price"` — the parameter's name — without a typo-prone quoted string. If you rename the parameter later, `nameof` follows automatically.
- `100m` — the `m` keeps the arithmetic in `decimal` (6.3: money is `decimal`).

The anti-pattern guards replace — the "arrow":

```csharp
// poor shape: everything nested under two layers of validity, main logic buried at the bottom
if (price >= 0)
{
    if (percentage >= 0 && percentage <= 100)
    {
        return price * percentage / 100m;   // hard to see, harder to extend
    }
}
```

Same semantics, worse shape: the reader must track *all* the conditions to reach the point. Guard clauses keep the happy path on the left margin.

#### 9.9 Worked decomposition — the mental move that builds applications

The skill this chapter has been arming you for: take a blob, find its natural parts, give each a name. Watch a 20-line blob become five methods — this is, in miniature, exactly how Part IV turns "a task app" into five files.

The blob (a poor man's task adder — all in one place):

```csharp
// BEFORE (poor): display + input + validation + creation + saving + confirmation, fused
Console.Write("Title: ");
string title = Console.ReadLine()?.Trim() ?? "";
if (string.IsNullOrWhiteSpace(title))
{
    Console.WriteLine("A title is required.");
    return;
}
TaskItem task = new TaskItem { Id = 1, Title = title };
// ... create, save, confirm ...
Console.WriteLine("Saved.");
```

Decompose — ask "what are the *different reasons* this might change?" and cut on those lines:

```csharp
// AFTER (good): each part named, each changeable alone
string title = ReadRequiredText("Title: ");   // input + validation (Ch. 7's helper)
TaskItem task = CreateTask(title);             // domain: build the object
Save(task);                                    // persistence
Confirm(task);                                // presentation
```

with each method single-purpose (`CreateTask` builds and returns a `TaskItem`; `Save` writes it somewhere; `Confirm` prints the message). Now: changing the *prompt* touches one method; changing *where* tasks are saved touches a different one; a designer could change the confirmation text without touching logic. **Each method is a wall with one door** — changes stay contained.

The test that you decomposed well: you can explain each method's behavior in one sentence, and its name *is* that sentence.

#### 9.10 Exercises

1. Write `static double Average(int a, int b, int c)` — returns the mean; remember 6.6's division trap.
2. Write `static bool IsEven(int n)` — expression-bodied, one line.
3. Write `static string DescribeNumber(int n)` — returns `"negative"`, `"zero"`, or `"positive"`; the compiler's "all paths return" rule (9.3) applies.
4. Write `ReadPassword()` — demands 8+ characters with at least one digit, re-asking until valid, and *returns the password* (input logic from 7.7, now in method form).
5. Add guards to `static long Factorial(int n)` — reject negative input with an exception, compute correctly for `0`..`20` (what happens at `21`, and why — 6.3?).

<details>
<summary><b>Solutions</b></summary>

**1.**

```csharp
static double Average(int a, int b, int c) => (a + b + c) / 3.0;
```

The `3.0` is the whole solution: `/ 3` would be integer division (6.6) and truncate. With `double` divisor the sum widens automatically.

**2.**

```csharp
static bool IsEven(int n) => n % 2 == 0;
```

**3.**

```csharp
static string DescribeNumber(int n)
{
    if (n < 0) return "negative";
    if (n > 0) return "positive";
    return "zero";
}
```

Note the last `return` has no `if` — after eliminating `<0` and `>0`, only `zero` remains, and the compiler sees all paths covered.

**4.**

```csharp
static string ReadPassword()
{
    while (true)
    {
        Console.Write("New password: ");
        string candidate = Console.ReadLine()?.Trim() ?? "";

        bool longEnough = candidate.Length >= 8;
        bool hasDigit = candidate.Any(char.IsDigit);

        if (longEnough && hasDigit)
        {
            return candidate;
        }
        Console.WriteLine("Needs 8+ characters and at least one digit.");
    }
}
```

**5.**

```csharp
static long Factorial(int n)
{
    if (n < 0)
    {
        throw new ArgumentOutOfRangeException(nameof(n), "Factorial is defined for non-negative numbers.");
    }

    long result = 1;
    for (int i = 2; i <= n; i++)
    {
        result *= i;
    }
    return result;
}
```

At `n = 21`: 21! exceeds `long.MaxValue` (≈9.2×10^18) — the multiplication silently overflows and wraps negative, *without* an exception, in normal code. The fix is a wider type (`decimal`? still too small — `System.Numerics.BigInteger`) or a guarded range. The lesson: choose a type by asking about the *largest possible value*, per 6.3 and Chapter 5's edge-case instinct.

</details>

---

### Chapter 10: Collections and Algorithms — Many Values at Once

> **In this chapter you will learn:** arrays and why indexing starts at zero; `List<T>` and what generics really are; `Dictionary<TKey,TValue>` for instant lookup by key; `HashSet<T>` for uniqueness; `Queue<T>` and `Stack<T>`; a decision table for choosing the right structure; your first genuine algorithm — linear search — traced line by line; sorting; and LINQ, the expressive query language over collections that Part IV uses constantly.
>
> **Prerequisites:** Chapters 6–9.

#### 10.1 The problem this chapter solves

One variable holds one value — but "the user's tasks", "the scores", "the names" are *many*. You could declare `task1`, `task2`, `task3`... until the 3 a.m. phone call when there are four. Collections are types that hold many values under one name, with the operations you need: add, remove, find, iterate, sort. Choosing the right collection is *the* central data decision of step 5 in the problem-solving process — this chapter makes you capable of making it.

#### 10.2 Arrays — fixed size, fastest access

An **array** is a fixed-length sequence of same-typed values, stored contiguously in memory:

```csharp
int[] scores = { 90, 75, 88 };

Console.WriteLine(scores[0]);      // 90 — first element (index ZERO)
Console.WriteLine(scores[2]);      // 88 — last element (index length-1)
Console.WriteLine(scores.Length);  // 3  — a property: how many slots

scores[1] = 80;                    // replace the second element
Console.WriteLine(scores[1]);      // 80
```

Word by word:

- `int[]` — the type: "array of `int`". The brackets mark "array".
- `{ 90, 75, 88 }` — an *initializer*: create with these values in this order.
- `scores[0]` — **indexing**: `arrayName[position]`. Positions start at **0**. (Why zero? The index is literally the *offset from the start* of the block of memory — `scores[0]` is "zero steps from the beginning." A 1970s hardware decision that became civilization-wide convention.)
- `.Length` — the number of slots, fixed at creation.
- `scores[1] = 80;` — write to a position.

The fixed length is the defining trade: arrays never resize. This makes them the fastest, leanest structure — and the most rigid: `scores[3] = 100;` (with only 3 slots) crashes with **`IndexOutOfRangeException`** at runtime. Valid indexes run `0` to `Length - 1` (8.10's lesson, now in its natural habitat).

When arrays are right: when the count is known and stable — a chess board (64), days of the week (7), the 3 test scores. When the count varies (tasks! names! log lines!), you need...

#### 10.3 `List<T>` — the workhorse

A `List<T>` is an ordered, resizable sequence:

```csharp
List<string> names = new List<string>();   // empty list, ready to grow

names.Add("Ari");                          // append at the end
names.Add("Bo");
names.Add("Cy");
Console.WriteLine(names.Count);            // 3 — Count, not Length (property of List)

names.Remove("Bo");                        // remove BY VALUE; shifts the rest left
Console.WriteLine(names.Count);            // 2 — ["Ari", "Cy"]

names.Add("Ari");                          // duplicates are allowed
Console.WriteLine(names[1]);               // "Cy" — indexed like an array
```

The `<T>` deserves its own paragraph — it is a **generic type parameter**, C# 2.0's crown feature:

- `List<string>` reads "a list *of strings*"; `List<int>` — "a list *of ints*"; Part IV: `List<TaskItem>` — "a list of tasks".
- `T` is a *placeholder* filled in at declaration: one list class, infinitely many safe instantiations.
- What safety means here: `List<string>` will refuse `names.Add(42)` *at compile time* (CS1503, argument type mismatch) — the mistake cannot even run. Before generics, programmers used lists of bare `object` and crashed at runtime on every cast. Generics moved the crash from your users to your compiler.

Reading `new List<string>()`: `new` — "construct a new object of this type" (Chapter 13 makes `new` precise); with C# 9's *target-typed new*, when the declared type is already stated you can abbreviate: `List<string> names = new();` — "new *of the type I just said*" — the form used throughout Part IV.

The everyday members:

| Member | Meaning |
|---|---|
| `Add(item)` | Append at the end |
| `Remove(item)` | Remove first occurrence of that *value* (returns `bool`: was it found?) |
| `RemoveAt(index)` | Remove by *position* |
| `Count` | How many items |
| `names[i]` | Read/write by index, 0-based |
| `Contains(item)` | Is this value present? (`bool`) |
| `Clear()` | Remove everything |

Iteration: `foreach (string name in names) { ... }` — 8.7's loop, over the list in order. Lists preserve insertion order — the third-added item stays in third position until removed. (That is why our task list remains stable across listings.)

#### 10.4 `Dictionary<TKey, TValue>` — lookup by key

A dictionary stores **key → value** pairs with near-instant retrieval by key — like a real dictionary (word → definition) or a contact book (name → number):

```csharp
Dictionary<int, string> namesById = new();

namesById[10] = "Ari";            // insert: associate key 10 with value "Ari"
namesById[20] = "Bo";

Console.WriteLine(namesById[10]); // "Ari" — instant lookup by key
Console.WriteLine(namesById.Count);        // 2

bool hasBo = namesById.ContainsKey(20);    // true
bool has30 = namesById.ContainsKey(30);    // false

if (namesById.TryGetValue(30, out string? found))   // the safe read pattern
{
    Console.WriteLine(found);
}
else
{
    Console.WriteLine("Key 30 not found.");          // this branch runs
}
```

Word by word:

- `Dictionary<int, string>` — keys are `int` (IDs), values are `string` (names). Two generic parameters.
- `namesById[10] = "Ari"` — the indexer used for writing: "under key 10, store Ari."
- `namesById[10]` — the indexer for reading. **Danger:** reading a *missing* key throws `KeyNotFoundException`. Which is why professionals use —
- `TryGetValue(key, out value)` — the `TryParse` pattern again (6.11): `true` + filled `out` variable when the key exists, `false` when not, no crash ever. The idiom to memorize.
- Keys are **unique**: `namesById[10] = "Dana"` replaces the previous value under 10 — one key, one value, last write wins.

When a dictionary is right: whenever *lookup by a meaningful key* is the core operation — find by ID, settings by name, word counts by word. Our Task Master looks tasks up by ID in Chapter 17 — with a list of a few hundred items, scanning is fine (Chapter 11 will say exactly when it is not).

#### 10.5 `HashSet<T>` — uniqueness as a data structure

A set stores **distinct** values with no order and a fast "is it in there?" answer:

```csharp
HashSet<string> tags = new();

tags.Add("work");
bool added = tags.Add("work");      // second attempt with the SAME value

Console.WriteLine(added);           // false — it was already there; not re-added
Console.WriteLine(tags.Count);      // 1
```

`Add` returns a `bool`: *did this insertion actually change the set?* That single boolean answers "have I seen this before?" in one call — the tool for deduplication, "seen" lists, and membership checks ("has the user already guessed this letter?").

#### 10.6 `Queue<T>` and `Stack<T>` — waiting lines and piles

Two structures that answer "what do I process next?" in opposite ways:

```csharp
Queue<string> printQueue = new();     // FIFO: First In, First Out — a fair waiting line
printQueue.Enqueue("doc1");           // join the line at the back
printQueue.Enqueue("doc2");
Console.WriteLine(printQueue.Dequeue());   // "doc1" — the first in is served first

Stack<string> undoStack = new();      // LIFO: Last In, First Out — a pile of plates
undoStack.Push("typed 'hello'");
undoStack.Push("deleted word");
Console.WriteLine(undoStack.Pop());   // "deleted word" — the LAST action is undone first
```

- **Queue = fairness**: printing queues, message processing, task scheduling.
- **Stack = reversal/recall**: undo history (Chapter 20's recursion also uses the call *stack* — the same idea inside the runtime).

#### 10.7 Choosing a collection — the decision table

| Your need | Reach for | Because |
|---|---|---|
| Fixed count, positions matter | `T[]` array | Fastest, leanest, no resizing overhead |
| Growing/shrinking ordered sequence | `List<T>` | Order preserved, append/remove cheap |
| Fast lookup by meaningful key | `Dictionary<TKey,TValue>` | Near-instant by-key access |
| Uniqueness / "seen before?" | `HashSet<T>` | Duplicate-free with one-call membership |
| First-come-first-served processing | `Queue<T>` | FIFO order is the whole point |
| Most-recent-first processing | `Stack<T>` | LIFO order is the whole point |
| Read-only view handed to callers | `IReadOnlyList<T>` | Consumers can read but cannot mutate — Part IV's public API type (17.3) |

How professionals actually choose: start from the **operations** the problem demands (step 5's questions: order? lookup? uniqueness? growth?), then pick the structure whose *strengths* match those operations. Structure follows operations — not habit, not fashion.

#### 10.8 Your first named algorithm — linear search

Chapter 1 promised: understanding before syntax. Here is the largest-number and "find it" thinking, now as a reusable method — one of the most fundamental algorithms in computing:

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

Line by line:

1. `static int FindIndex(int[] numbers, int target)` — name says it; returns an `int` (the position); takes the collection and the value sought as parameters — data in, answer out (9.7's rules).
2. `for (int index = 0; index < numbers.Length; index++)` — visit every valid position: `0` to `Length - 1`, the exact safe range (8.10).
3. `if (numbers[index] == target)` — compare the item at this position with what we seek.
4. `return index;` — found: hand back the position. `return` inside a loop ends the method *instantly* — later items are never examined (that is the "found it, stop" behavior, and it is correct: we promised the *first* match).
5. `return -1;` — the loop finished with no match: report **not found**. Why -1? It is *impossible* as a real index (those start at 0), so it can unambiguously mean "absent" — a tiny piece of API design: make error values distinguishable from real ones.

Trace it — `FindIndex(new[] { 90, 75, 88 }, 75)`:

| `index` | `numbers[index]` | `== 75`? | What happens |
|---|---|---|---|
| 0 | 90 | false | loop continues |
| 1 | 75 | **true** | `return 1` — done |

The pattern generalizes to *any* collection and *any* matching predicate — Chapter 17's `Search` finds tasks by title/description using exactly this scan, expressed in LINQ.

#### 10.9 Sorting — order on demand

Sorting is so common that you should essentially never hand-write it (the library's sort is decades-tuned) — but you must understand what it *is*: repeatedly comparing and swapping until no adjacent pair is out of order, `O(n log n)` in the library (Chapter 11 prices it):

```csharp
int[] numbers = { 5, 1, 4, 2 };
Array.Sort(numbers);                       // sorts in place: {1, 2, 4, 5}

List<int> values = new() { 9, 3, 7 };
List<int> sortedCopy = values.OrderBy(v => v).ToList();   // LINQ: sorted COPY (original untouched)
```

Two flavors with a deep difference: `Array.Sort` mutates the original; `OrderBy` produces a *new, sorted view* — the non-destructive form that pervades Part IV (we sort for display; we do not scramble the underlying storage).

#### 10.10 LINQ — asking questions of collections

**LINQ** (**L**anguage **IN**tegrated **Q**uery, C# 3.0) is a set of methods that express *queries over collections* as readable chains. You have already seen `Any` (Chapter 7's solution); here is the core set, all used in Part IV:

```csharp
List<int> numbers = new() { 5, 1, 4, 2, 8 };

List<int> sorted   = numbers.OrderBy(n => n).ToList();          // ascending: 1,2,4,5,8
List<int> big      = numbers.Where(n => n > 3).ToList();        // filter: 5,4,8
List<int> doubled  = numbers.Select(n => n * 2).ToList();      // transform: 10,2,8,4,16
bool     anyBig    = numbers.Any(n => n > 7);                  // true — at least one
bool     allSmall  = numbers.All(n => n < 10);                 // true — every single one
int      first     = numbers.First(n => n > 3);                // 5 — first match (crashes if none!)
int?     firstOr0  = numbers.FirstOrDefault(n => n > 100);     // 0 — first match OR default
int      max       = numbers.Max();                            // 8
int      min       = numbers.Min();                            // 1
int      count     = numbers.Count(n => n % 2 == 0);           // 2 — how many satisfy the test
```

The magic-looking `n => n > 3` is a **lambda expression** — a tiny anonymous function, dissected word by word:

| Piece | Meaning |
|---|---|
| `n` | The input parameter — one item from the collection, supplied by LINQ on each pass |
| `=>` | The "goes to" arrow — separates input from body |
| `n > 3` | The body: an expression producing a `bool` (for filters) or a value (for `Select`) |

Read `Where(n => n > 3)` aloud: "give me the items — call each one `n` — where `n > 3`." The lambda is your test, applied to every element in turn. LINQ is the *fusion* of Chapter 8's loops and Chapter 9's methods: a loop you can read as a sentence.

The `.ToList()` calls: LINQ methods are **lazy** — `numbers.Where(...)` alone builds the *plan* of a query and executes nothing; `.ToList()` (or a `foreach`) forces it to run and materialize results. Non-obvious, but only one habit is needed: end your chains with `ToList()` in console apps and everything behaves.

One sharp edge to memorize now: `First` **throws** when nothing matches; `FirstOrDefault` returns a default (`0`/`null`) instead. Rule: `First` only when absence is *impossible* (you just checked with `Any`); `FirstOrDefault` when absence is a real possibility — exactly how Part IV looks up task IDs:

```csharp
TaskItem? task = tasks.FirstOrDefault(t => t.Id == id);   // null when no such task — never crashes
```

#### 10.11 Exercises

1. Build a `List<int>` of five scores; print each with its position (`0: 90` style); print the largest and smallest **without** LINQ (use a running champion — 8.12's pattern), then with LINQ (`Max`/`Min`).
2. Write a word-frequency counter: given `List<string> words`, produce a `Dictionary<string, int>` of counts. What single structure feature gives you the deduplication for free?
3. A log file must keep the last 100 events. Which structure fits if old events should be dropped in arrival order? Write the add-with-limit loop.
4. Using the list from exercise 1, write one LINQ chain: only even numbers, sorted descending, as strings — in one statement.
5. Predict the output, then run:

```csharp
var set = new HashSet<string> { "a", "b" };
Console.WriteLine(set.Add("a"));
Console.WriteLine(set.Count);

var dict = new Dictionary<string, int>();
dict["x"] = 1;
dict["x"] = 2;
Console.WriteLine(dict["x"]);

var list = new List<int> { 1, 2, 3 };
Console.WriteLine(list.FirstOrDefault(n => n == 5));
```

<details>
<summary><b>Solutions</b></summary>

**1.**

```csharp
List<int> scores = new() { 90, 75, 88, 60, 95 };

for (int i = 0; i < scores.Count; i++)
{
    Console.WriteLine($"{i}: {scores[i]}");
}

int champion = scores[0];                 // running-champion algorithm (Ch. 1)
foreach (int s in scores)
{
    if (s > champion) champion = s;
}
Console.WriteLine($"Largest: {champion}, smallest: {scores.Min()}");   // 95, 60
```

**2.**

```csharp
Dictionary<string, int> counts = new();

foreach (string word in words)
{
    if (counts.TryGetValue(word, out int current))
    {
        counts[word] = current + 1;
    }
    else
    {
        counts[word] = 1;      // first sighting
    }
}
```

The dictionary's **unique keys** give deduplication for free — each distinct word becomes exactly one entry whose value counts occurrences. (LINQ's `GroupBy` can do this in one chain, but this explicit loop is the version you should be able to write first.)

**3.** A `Queue<T>` — arrival order *is* a queue; when `Count` reaches 100, `Dequeue()` the oldest before `Enqueue()`-ing the new:

```csharp
Queue<string> events = new();

void AddEvent(string line)
{
    if (events.Count == 100)
    {
        events.Dequeue();       // drop the oldest
    }
    events.Enqueue(line);       // append the newest
}
```

**4.**

```csharp
List<string> result = scores
    .Where(n => n % 2 == 0)
    .OrderByDescending(n => n)
    .Select(n => n.ToString())
    .ToList();
```

Read it as the sentence it is: "take the scores, keep evens, order descending, make each a string." Order of operations matters: filter *before* sorting (fewer items to sort), sort before select (we sort by number, not by string!).

**5. Predicted output:**

```text
False     — Add("a") on an existing member: nothing changed
2         — "a" and "b"
2         — duplicate key: last write wins (10.4)
0         — no match → FirstOrDefault's default for int
```

</details>

---

### Chapter 11: Complexity — Choosing an Algorithm That Scales

> **In this chapter you will learn:** why "correct" is not enough when input grows; how to read Big O notation (the standard vocabulary of cost); the common complexity classes with concrete meanings; binary search — implemented, traced line by line, and proven logarithmic; the six questions that guide algorithm choice; and the professional discipline of measuring before optimizing.
>
> **Prerequisites:** Chapters 8, 10 (loops, arrays, linear search).

#### 11.1 The problem this chapter solves

Two solutions can both be correct — and one of them can be a million times slower. Chapter 10's linear search scans every item; fine for 100 tasks, painful for 10 million. **Complexity** is how we talk about the way an algorithm's cost *grows with input size* — the skill that lets you choose between solutions before writing either one, and the shared vocabulary of every technical interview you will ever take.

#### 11.2 Cost you can feel — the growth table

Imagine each "step" of an algorithm takes one microsecond, and the input has `n` items:

| Algorithm class | n = 100 | n = 10,000 | n = 1,000,000 |
|---|---|---|---|
| `O(1)` — constant | 0.000001 s | 0.000001 s | 0.000001 s |
| `O(log n)` — logarithmic | 0.000007 s | 0.000014 s | 0.000020 s |
| `O(n)` — linear | 0.0001 s | 0.01 s | 1 s |
| `O(n log n)` — linearithmic | 0.0007 s | 0.13 s | ~20 s |
| `O(n²)` — quadratic | 0.01 s | 100 s | ~11.6 days |
| `O(2ⁿ)` — exponential | unmeasurable | heat death | heat death |

Read the columns, not just the rows. `O(log n)` barely moves as `n` explodes: a million items cost only ~20 steps — because each step *halves* the remaining work. `O(n²)` collapses: doubling input quadruples cost; nested loops (8.9) are this shape. The whole discipline of this chapter is: **recognize which class your idea belongs to, and prefer smaller classes when the data can grow.**

#### 11.3 Big O — the formal little idea

**Big O notation** describes how the *worst-case* cost of an algorithm grows as input size `n` grows, *ignoring constants*:

- Constants dropped: an algorithm doing `3n + 25` operations is `O(n)` — the `3` and `25` vanish because *growth shape* is what we compare, not exact stopwatch numbers (constants vary by machine; growth does not).
- We track the **dominant term**: `n² + n` is `O(n²)` because for large `n`, the `n²` part dwarfs the rest.

The classes with their signatures:

| Notation | Informal name | Growth intuition | Where you have already met it |
|---|---|---|---|
| `O(1)` | Constant | Cost independent of size | Array access `a[i]`; dictionary lookup by key |
| `O(log n)` | Logarithmic | Halve the problem each step | Binary search (11.4) |
| `O(n)` | Linear | Touch every item once | Linear search (10.8); one `foreach` |
| `O(n log n)` | Linearithmic | Sort-like cost | Library sorting (`OrderBy`, `Array.Sort`) |
| `O(n²)` | Quadratic | Every item × every item | Nested loops over the same collection (8.9) |
| `O(2ⁿ)` | Exponential | Doubling per item | Trying every subset; naive recursion gone wild (20.3) |

How to *estimate* the class of code you wrote — count the loops that touch the data:

- Straight-line code, no loop over the data: `O(1)`.
- One loop over the data: `O(n)`.
- A loop over the data, containing another loop over the data: `O(n²)`.
- A loop where the data *shrinks by half* each iteration: `O(log n)`.
- Sort + a linear pass: `O(n log n)` — the sort dominates the pass.

#### 11.4 Binary search — the logarithm made visible

Linear search (10.8) treats unsorted data fairly: check everything. But **if the data is sorted, you can throw away half of it with every comparison**. That is binary search — the algorithm humans use instinctively in a paper dictionary: open near the middle, decide which half your word cannot be in, repeat.

Requirements: the data must be **sorted**. The payoff: `O(log n)` — for 1,000,000 items, about 20 comparisons.

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

Line by line — every line earns its place:

1. `int low = 0;` and `int high = numbers.Length - 1;` — two fence posts enclosing the *region that might still contain the target*. Initially: the whole array. `low` is the first candidate index, `high` the last (8.10's `length - 1`).
2. `while (low <= high)` — "the region is not empty." The instant `low` passes `high`, every index has been eliminated → not found. This comparison (`<=`, not `<`) is *the* classic off-by-one battleground of this algorithm.
3. `int middle = low + (high - low) / 2;` — the midpoint of the region. Written this way — instead of the tempting `(low + high) / 2` — because `low + high` can overflow a 32-bit `int` for huge arrays (6.3's edges, in a real algorithm from the JDK's own history: this exact bug lived in Java's library for years).
4. `if (numbers[middle] == target) return middle;` — found it: the answer is the position.
5. `if (numbers[middle] < target)` — the target is *larger* than the middle value → the target can only be **to the right** (sorted data!), so: `low = middle + 1;` — the entire left half *and* `middle` itself are eliminated in one move.
6. `else high = middle - 1;` — symmetric: target smaller → eliminate the right half.
7. `return -1;` — loop ended with an empty region: not found (10.8's sentinel convention).

Now *watch the halving* — search for `7` in `{1, 3, 5, 7, 9, 11}` (6 items; indexes 0–5):

| Iteration | `low` | `high` | region (indexes) | `middle` | `numbers[middle]` | Decision |
|---|---|---|---|---|---|---|
| 1 | 0 | 5 | 1 3 5 **7** 9 11 | 2 | 5 | 5 < 7 → go right: `low = 3` |
| 2 | 3 | 5 | **7** 9 11 | 4 | 9 | 9 > 7 → go left: `high = 3` |
| 3 | 3 | 3 | **7** | 3 | 7 | found → return `3` |

Six items, three steps. The pattern scales terrifyingly well: 1,000,000 sorted items need at most **20** steps (`log₂ 1,000,000 ≈ 19.9`), because each step halves the region — after 20 halvings nothing remains. That is what `O(log n)` *means*: cost proportional to the number of halvings, not to the size.

The trade-off, honestly stated: binary search demands sorted data — and *keeping data sorted* costs `O(n log n)` per re-sort (or careful insertion). Sorted once + searched many times → binary search wins brilliantly; shuffled constantly + rarely searched → keep linear scan simple. **This is the "choose data by operations" principle (10.7) repriced in cost units.**

#### 11.5 Choosing an algorithm — the six questions

Before committing to an approach, ask (in rough order):

1. **Is the data already sorted?** (Sorted → binary search becomes free to use; unsorted → sorting costs `O(n log n)` first.)
2. **How large can `n` really become?** For 50 tasks, *anything* works — pick the clearest code. For 50 million rows, classes matter. (This is the question beginners forget and professionals never do.)
3. **Is memory constrained?** Building a `Dictionary` for speed trades RAM for time — sometimes right, sometimes impossible.
4. **Is the answer needed once, or repeatedly?** Once → scan simply. Repeatedly → pay for preprocessing (sort/index once), amortize it across queries.
5. **Can preprocessing make repeated work cheaper?** (Same idea, inverted: a 100-query workload justifies one `O(n log n)` sort.)
6. **Is correctness or speed the primary concern?** Under correctness pressure, choose the simple provable version first — always.

#### 11.6 The discipline: correct baseline first, measure, then optimize

Two professional rules that prevent the two classic sins:

1. **Premature optimization is a bug factory.** Making code fast *before it is correct and clear* means optimizing the wrong thing: get a correct baseline, *measure* where time actually goes (`dotnet trace`, profilers — Chapter 21 territory), and optimize only the demonstrated hotspot.
2. **Complexity analysis is a design tool, not a mandate.** An `O(n)` scan over a list that will hold 200 tasks is *finished code*; replacing it with an indexed dictionary "because O(1)" for that workload is waste. Choose classes for the workload you have — which is exactly why Task Master's Chapter 17 scans its list and that is the right call at this scale.

Applied posture for everything you will build: **correct, clear, then fast enough** — in that order, with measurement as the referee.

#### 11.7 Exercises

1. Classify the cost: (a) one `foreach` over a list printing each item; (b) two nested `foreach` loops comparing every pair; (c) `dictionary[key]`; (d) sorting then one pass; (e) binary search on a sorted array.
2. Your search runs `O(n)` over 1,000,000 rows and takes 1 second. A colleague proposes an `O(n²)` alternative that is "simpler." Respond with numbers.
3. Trace binary search by hand for target `4` in `{2, 4, 6, 8, 10, 12, 14}` — table it like 11.4. How many iterations?
4. The task list is sorted by ID and users search by *title text*. Does binary search apply? What does?
5. Extra credit: why is `middle = (low + high) / 2` a bug, while `low + (high - low) / 2` is safe? Give a number scenario.

<details>
<summary><b>Solutions</b></summary>

**1.** (a) `O(n)`; (b) `O(n²)`; (c) `O(1)`; (d) `O(n log n)` (sort dominates the linear pass); (e) `O(log n)`.

**2.** The "simpler" version implies ~10^12 operations — at the same rate, roughly **11.6 days** per run instead of 1 second (the 11.2 table, quoted). Simplicity that costs five orders of magnitude is not simplicity; the colleague should justify with a measured workload, or be quietly shown the growth table.

**3.** `{2,4,6,8,10,12,14}`, target 4:

| Iteration | `low` | `high` | `middle` | value | Decision |
|---|---|---|---|---|---|
| 1 | 0 | 6 | 3 | 8 | 8 > 4 → `high = 2` |
| 2 | 0 | 2 | 1 | 4 | found → return `1` |

Two iterations — found at the second probe. (`log₂ 7 ≈ 2.8` upper bound; lucky halving found it early.)

**4.** No — binary search applies only to the *sorted key* (IDs), not to free text. Title search is a *filter*, not a position lookup: linear scan with `Contains` (10.8's generalized pattern) is the correct `O(n)` answer at this scale — as implemented in Chapter 17.

**5.** `low + high` can overflow: with `low = 2,000,000,000` and `high = 2,100,000,000` (huge arrays on 64-bit with 32-bit indexes), the sum wraps negative, and a negative `middle` indexes wildly (or crashes). `high - low` is guaranteed small and non-negative, so `low + (small / 2)` can never overflow. A famous real-world bug — binary search looked correct for decades until arrays got big enough.

</details>

---

### Chapter 12: Debugging and Testing — Finding Bugs Before Users Do

> **In this chapter you will learn:** the three species of error and their tells; a systematic 10-step debugging procedure (vs the random-tweak anti-procedure); how to use breakpoints and stepping in an IDE; assertions and guard exceptions as self-defense; the Arrange–Act–Assert pattern; how to create and run a real xUnit test project; and the checklist of what to test.
>
> **Prerequisites:** Chapters 6–11.

#### 12.1 The problem this chapter solves

Programs do not run; they *are run*, and errors divide cleanly into three species. Knowing the species tells you which tool hunts it — and most "debugging pain" is actually species misidentification, random edits applied to a bug that needed evidence instead.

#### 12.2 The three species of error

**Species 1: Compile-time errors.** The compiler cannot understand or type-check your program. It never runs, and the compiler tells you exactly where and why (Chapter 4.8).

```csharp
int age = "twenty";
```

```text
error CS0029: Cannot implicitly convert type 'string' to 'int'
```

*Tell:* appears in the build output; program never started. *Hunter:* read the message; fix the line. These errors are *good news* — the cheapest you will ever fix.

**Species 2: Runtime errors.** The program compiles and starts, then fails *during* execution when reality violates an assumption:

```csharp
int[] scores = { 90, 75, 88 };
Console.WriteLine(scores[5]);      // compiles fine — then dies: IndexOutOfRangeException
```

*Tell:* the program starts, then crashes with an exception and (in .NET) a stack trace — the list of methods that were active when the failure happened. *Hunter:* the trace names the line and the failure; fix the *assumption* (index bounds, missing file, null, divide by zero), not just the symptom line. Chapter 14 teaches catching them gracefully.

**Species 3: Logic errors.** The program runs *successfully* and produces a wrong result. No message, no crash — a silent wrong answer:

```csharp
double average = (a + b + c) / 3;    // a,b,c are int → integer division truncated first
```

*Tell:* only your **tests** and your predictions reveal it (which is why Chapter 4's "predict before running" and Chapter 5's examples exist). *Hunter:* systematic testing + debugging procedure. These are the most dangerous species precisely because the computer is perfectly happy — it checks syntax and types, not intentions.

#### 12.3 The debugging procedure — evidence over guessing

Print this once and follow it forever:

1. **Reproduce reliably.** A bug that appears "sometimes" is a bug you cannot fix. Find the exact input sequence that always triggers it.
2. **Record the exact input.** Write down (or save) the failing input — it is your regression test's raw material (step 10).
3. **State the expected result.** From the spec/examples (Chapter 5's tables): what *should* happen.
4. **State the actual result.** What *does* happen. Steps 3–4 together are "the bug" — many "bug reports" are missing one of the two.
5. **Find the smallest failing example.** Delete input until the failure stops: the last thing you removed before it stopped working is implicated. A bug that fails on 3 items but not 4 narrows itself drastically.
6. **Inspect values at suspicious points.** Breakpoints (12.4) or temporary prints: what is `middle`? what did `ReadLine` actually return? — a variable holding a *surprising* value is a lead.
7. **Form ONE hypothesis.** "The parse fails on trailing spaces because I never trim." One, not three — science, not shotgun surgery.
8. **Make ONE change.** The smallest change that tests the hypothesis.
9. **Re-run the same test.** Same input, same expectation. If fixed — continue; if not — you falsified a hypothesis, which is also progress: now you know more.
10. **Add a regression test.** Encode the failing input as a test (12.5) so this bug can never silently return — the bug fix is not complete until the test exists.

The anti-procedure, for contrast: *change something, run, change something else, run, mutter, "clean" the code, run, rearrange, run...* — this is how a one-line bug becomes a rewritten module with three new bugs. The difference between debuggers and dabblers is exactly the difference between steps 1–10 and the anti-procedure.

#### 12.4 Breakpoints and stepping — the X-ray machine

Every serious editor (VS Code with the C# extension, Visual Studio, Rider) gives you a **debugger**: a machine that pauses your program mid-flight so you can examine it.

- **Breakpoint**: click the gutter (left margin) next to a line — a red dot appears. Run with the debugger (`F5` in VS Code); when execution *reaches* the line, the program freezes **before** running it.
- While paused, inspect: **local variables** (current values — the surprising one is your lead), **method parameters** (did the arguments arrive intact?), **the call stack** (which chain of methods led here), and the **next line to execute**.
- **Stepping modes** — the three verbs:
  - **Step Over** (`F10`): run the current line, *including* everything it calls, and pause at the next line. Your everyday verb.
  - **Step Into** (`F11`): if the current line calls a method, *enter* it and pause at its first line. When you suspect the called method.
  - **Step Out** (`Shift+F11`): finish the current method and pause back in the caller. When you stepped into something that turns out innocent.

The debugging rhythm: break where reality starts to look wrong → inspect → step over a few lines → watch the moment a variable goes bad → form the hypothesis → fix → re-run (12.3's steps 6–9, mechanized).

#### 12.5 Assertions — making the program check *you*

An **assertion** is a statement that a fact *must* hold at a given point — a tripwire that turns a silent species-3 logic error into a loud, immediate, localized species-2 failure:

```csharp
if (total < 0)
{
    throw new InvalidOperationException("Total cannot be negative — a calculation is wrong upstream.");
}
```

Placed at method entry (guard clauses, 9.8) or after a calculation, it says: *if this "impossible" thing happens, stop the world here, at the scene of the crime* — not three methods later where the corrupted value surfaces. Cheap to write, priceless when they fire.

#### 12.6 Unit testing — making correctness repeatable

A **unit test** is a small program whose only job is to call your code with known inputs and compare actual output against expected. The payoff: *every* run re-verifies everything; a fix that breaks an old feature is caught in seconds, not in production.

The universal structure is **Arrange–Act–Assert** (AAA):

```text
Arrange:  create the exact input situation
Act:      call the method under test
Assert:   compare the actual result with the expected result
```

In C#, the standard tool is **xUnit**. Create a test project next to your application project and link them (the commands below use the Task Master project you will complete in Part IV — if you are reading ahead, treat the example as a preview of Chapter 19, where the test project is created for real):

```bash
dotnet new xunit -n TaskMaster.Tests
dotnet add TaskMaster.Tests reference TaskMaster
```

Word by word: `dotnet new xunit -n TaskMaster.Tests` — scaffold a project from the *xUnit template* (naming it per convention: application name + `.Tests`); `dotnet add ... reference ...` — "make the test project *see* the application project's public types."

A complete test, annotated line by line:

```csharp
using TaskMaster.Services;   // import the application's types
using Xunit;                 // import the test framework: attributes + Assert

namespace TaskMaster.Tests;

public class TaskValidatorTests     // a container class; one per tested class, by convention
{
    [Fact]                        // xUnit attribute: "the method below is ONE test fact"
    public void EmptyTitle_ReturnsAnError()     // name = scenario_expected outcome
    {
        // Arrange — the input known to be invalid
        string candidate = "   ";

        // Act — the single behavior under test
        string error = TaskValidator.ValidateTitle(candidate);

        // Assert — the promised outcome
        Assert.Equal("A title is required.", error);
    }

    [Fact]
    public void NormalTitle_ReturnsNoError()
    {
        string error = TaskValidator.ValidateTitle("Learn C#");   // arrange + act
        Assert.Equal(string.Empty, error);                          // assert
    }
}
```

- `[Fact]` — attribute (square brackets = metadata attached to code) that xUnit's runner discovers and executes as one test.
- `Assert.Equal(expected, actual)` — the comparison that decides pass/fail; xUnit offers `Assert.True`, `Assert.Throws<T>` (asserts that an exception *is* thrown — perfect for 9.8's guards), `Assert.Null`, and more. Note the argument order convention: *expected first*.
- Test **naming matters**: `EmptyTitle_ReturnsAnError` — when it fails in a list of 200 tests, the name alone tells you what broke.
- The runner: `dotnet test` — compiles both projects, discovers all `[Fact]` methods, runs them, prints pass/fail per test. Green output:

```text
Passed! - Failed: 0, Passed: 2
```

#### 12.7 What to test — the category checklist

For each behavior, deliberately cover (Chapter 5's edge-case instincts, now mechanized):

- **Normal cases** — the happy path from your examples table.
- **Empty / zero / null** — the presence-absence boundary.
- **Minimum and maximum** — `0`, `int.MaxValue`, the first and last element.
- **Invalid input** — wrong type, malformed data, out-of-range.
- **Duplicates** — same title twice, same ID twice.
- **Behavior after operations** — does add-then-delete leave state clean? (Actions interact; single-action tests miss interaction bugs.)
- **Persistence failures** — missing file, corrupted file (Chapter 16's scenarios — infrastructure tests).

A pragmatic rule for proportion: tests concentrate where the *rules* live (validation, ID logic, state transitions) — a professional suite is dense over rules, light over input/output plumbing.

#### 12.8 The regression discipline — bugs as gifts

Every bug you ever find becomes, after the fix, a permanent test — step 10 of the procedure. The suite only grows, and the accumulated tests are exactly the memory of "mistakes this codebase has already made once" — which is why mature projects' test suites are their most honest documentation.

#### 12.9 Exercises

1. Classify the species, each with a one-line reason: (a) `CS1002: ; expected`; (b) `List index out of range` mid-run; (c) a program that prints `-20` years until retirement for a 40-year-old.
2. Debug-procedure practice: a program crashes "sometimes" — write the first three concrete actions you take (no code, just procedure).
3. Write two `[Fact]` tests for `IsEven(int n)` from 9.10 — one for an even value, one odd. What naming would survive a 200-test failure list?
4. Write an AAA test for `CalculateDiscount(80m, 10m)` (9.8) asserting the exact returned value — then one for the guard: `Assert.Throws<ArgumentOutOfRangeException>` for `-1m, 10m`.
5. Which steps of the debugging procedure does a breakpoint *mechanize*? (12.3's numbers vs 12.4's tools.)

<details>
<summary><b>Solutions</b></summary>

**1.** (a) Compile-time — the compiler found it before running; (b) runtime — valid program, invalid assumption executed; (c) logic — runs clean, answers wrong (the `20 - age` example of Chapter 1, species 3 in the flesh).

**2.** (1) Make it reproduce reliably — pin the exact input sequence, counting "sometimes" until it is "always"; (2) record the exact input and keep it; (3) state expected vs actual precisely. Then (and only then) break out the debugger and form one hypothesis.

**3.**

```csharp
[Fact] public void Four_IsEven()       => Assert.True(IsEven(4));
[Fact] public void Three_IsNotEven()    => Assert.False(IsEven(3));
```

Names state input and expected outcome — readable in any failure list.

**4.**

```csharp
[Fact]
public void TenPercentOfEighty_IsEight()
{
    decimal result = CalculateDiscount(80m, 10m);   // act (arrange is inline constants)
    Assert.Equal(8m, result);
}

[Fact]
public void NegativePrice_IsRejected()
{
    Assert.Throws<ArgumentOutOfRangeException>(() => CalculateDiscount(-1m, 10m));
}
```

The lambda `() => CalculateDiscount(...)` is "defer: run this inside the assert" — `Throws` calls it and captures the exception to verify. The negative-price behavior is *guarded at the door* (9.8), and now the door is under permanent surveillance.

**5.** Step 6 (inspect values at suspicious points) — breakpoints and the variables window are that step, mechanized; step 9's "re-run the same test" is the debugger's restart button. Everything else — reproducing, hypothesizing, the one-change rule — remains *yours*; the tool provides evidence, you provide the science.

</details>

---

### Chapter 13: Object-Oriented Problem Solving — Organizing a Growing Program

> **In this chapter you will learn:** the problem object orientation solves; class vs object (blueprint vs instance), with the constructor; the anatomy of a class in full; encapsulation with properties; abstraction with interfaces; inheritance and polymorphism — used sparingly; composition, the everyday alternative; and when *not* to reach for OOP.
>
> **Prerequisites:** Chapters 6–12. From here on, this chapter's vocabulary is the structural language of Part IV.

#### 13.1 The problem this chapter solves

By Chapter 12 your programs are competent — but imagine the Task Manager as one giant method: menu code, validation, ID math, file reading, JSON parsing, error messages, all in one 300-line block. Change the menu and you might break the JSON. Add a field and you re-test *everything*. This is the **big ball of mud**, and it is what happens when a program's *data* and the *rules about that data* live apart, with every function reaching into everything.

Object orientation's insight: **group data with the rules that protect it, and name the group.** Then a program becomes a small number of well-defined things collaborating — each understandable alone, each changeable alone. Part IV's five-file architecture is exactly this chapter applied.

#### 13.2 Class and object — blueprint and house

- A **class** is a *blueprint*: a description of data (fields/properties) and behavior (methods) that some kind of thing will have.
- An **object** is an *instance*: a real thing built from that blueprint, with its own live values.

One blueprint (`TaskItem`), many objects (`task #1`, `task #2`...) — each with its own `Id`, `Title`, `Status`, but all sharing the same *shape* of capabilities.

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

Building and using instances:

```csharp
Counter first = new Counter();     // "new" = construct an object from the blueprint
Counter second = new Counter();    // a SEPARATE object — its own Value

first.Increase();
first.Increase();

Console.WriteLine(first.Value);     // 2
Console.WriteLine(second.Value);    // 0 — untouched; objects do not share their fields
```

Word by word: `new Counter()` — the **`new` operator** allocates memory for a fresh `Counter` and runs its **constructor** (below), returning a reference to it (6.4: the variable holds an arrow to the object, which is why `first` and `second` staying independent matters). `first.Increase()` — "call the `Increase` behavior *on the object `first`*" — the `.` selects a member; the behavior reads and writes *that object's* fields.

#### 13.3 Anatomy of a class — every piece named

A fuller example, with every part you will meet in Part IV:

```csharp
public class BankAccount
{
    private decimal _balance;                        // 1. field

    public string Owner { get; }                     // 2. read-only property

    public decimal Balance                           // 3. computed property
    {
        get { return _balance; }
    }

    public BankAccount(string owner)                 // 4. constructor
    {
        Owner = owner;
        _balance = 0;
    }

    public void Deposit(decimal amount)              // 5. method
    {
        if (amount <= 0)
        {
            throw new ArgumentOutOfRangeException(nameof(amount));
        }
        _balance += amount;                          // rule lives WITH the data
    }

    public bool TryWithdraw(decimal amount)          // 6. method returning a status
    {
        if (amount > _balance)
        {
            return false;                            // insufficient funds: refuse politely
        }
        _balance -= amount;
        return true;
    }
}
```

The pieces:

1. **Field** (`private decimal _balance;`) — a variable stored *inside* each object, one per instance (13.2's experiment). `private` = visible only within the class: the outside world cannot even see it.
2. **Property** (`public string Owner { get; }`) — a named value exposed to the outside, with a `get` (readable) and/or `set` (writable). `{ get; }` = readable only, settable only inside construction. Properties are how a class *publishes* data safely.
3. **Computed property** (`Balance`) — a property whose `get` returns a calculation; to callers it *looks* like a field, which is the point: callers should not know or care whether a value is stored or derived.
4. **Constructor** (`public BankAccount(string owner)`) — a special method that runs *during* `new`. Same name as the class, no return type. Its job: make the object start **valid** — every field given a sane value before anyone can use the object. "No `BankAccount` can ever exist without an `Owner`" is a rule enforced by construction.
5. & 6. **Methods** — the behaviors. `Deposit` *enforces a rule* (`amount <= 0` → guard exception, 9.8) while changing the data; `TryWithdraw` encodes a *business rule* (no negative balances) and reports success politely (the `TryParse` pattern of 6.11, now for domain rules).

The naming law of members: `public` members (`PascalCase`) are the class's *promises* to the world; `private` members (`_camelCase`) are its *secrets*. A class should be understandable from its `public` side alone.

#### 13.4 Encapsulation — the bodyguard principle

**Encapsulation** = data and the rules protecting it live together, with the data hidden and the rules exposed:

```csharp
public int Value { get; private set; }
```

Read that property line word by word: `public int Value` — the outside world can *read* `Value`; `{ get; }` — the getter is public; `private set;` — the setter is private: **only code inside the class may assign it**. Net effect: `counter.Value = 100;` from outside is a compile error (CS0122 or CS8852) — while `counter.Increase();` is the *only door* to changes, and `Increase` can enforce whatever rules it wants.

Compare the unprotected alternative: `public int Value;` — anyone, anywhere, sets `Value` to `int.MinValue` on a whim; every rule about `Value` is now a matter of hope. Encapsulation replaces hope with construction: **make invalid states hard or impossible to reach**, and a whole category of bugs (who set this? where?) simply cannot occur, because every change passes one guarded door.

#### 13.5 Abstraction and interfaces — promising behavior

**Abstraction** = expose *what* something does; hide *how*. Its sharpest tool is the **interface** — a pure contract of members, no implementation:

```csharp
public interface IClock
{
    DateTime UtcNow { get; }        // any IClock must provide "the current UTC time"
}
```

A class *implements* an interface — signs the contract:

```csharp
public sealed class SystemClock : IClock
{
    public DateTime UtcNow => DateTime.UtcNow;
}

public sealed class FrozenClock : IClock          // a test double (12.6's best friend)
{
    public DateTime UtcNow => new DateTime(2026, 11, 9, 8, 0, 0, DateTimeKind.Utc);
}
```

Why this matters enormously in practice: a component that needs time should *depend on `IClock`*, not on the machine clock:

```csharp
public sealed class TaskManager
{
    private readonly IClock _clock;               // the DEPENDENCY is the contract

    public TaskManager(IClock clock)              // caller chooses the implementation
    {
        _clock = clock;
    }

    public TaskItem Add(string title)
    {
        // ...
        TaskItem task = new() { Title = title, CreatedAt = _clock.UtcNow };  // created via the contract
        // ...
        return task;
    }
}
```

In production: `new TaskManager(new SystemClock())` — real time. In a test: `new TaskManager(new FrozenClock())` — **the exact same code paths run against a frozen, deterministic instant**: "task created on 2026-11-09" becomes an assertable fact instead of a clock race. Abstraction is what makes code *testable* (12.6) — a point beginners usually meet only after their first flaky date test.

Naming: interfaces conventionally start with `I` (`IClock`, `INotifier`, and in the wild `IRepository`, `ILogger`) — "I" = "I am a contract."

#### 13.6 Inheritance and polymorphism — the "is-a" family

**Inheritance** lets one class *extend* another, gaining its members and specializing them: `class Dog : Animal` — "a Dog *is an* Animal, plus more." **Polymorphism** is the payoff: code written against the parent type works, *appropriately*, on every child:

```csharp
public interface INotifier
{
    void Notify(string message);
}

public sealed class ConsoleNotifier : INotifier
{
    public void Notify(string message) => Console.WriteLine(message);      // writes to terminal
}

public sealed class CompositeNotifier : INotifier                          // a notifier of notifiers
{
    private readonly INotifier[] _children;
    public CompositeNotifier(params INotifier[] children) => _children = children;

    public void Notify(string message)
    {
        foreach (INotifier child in _children)
        {
            child.Notify(message);         // EACH child does its OWN thing with the same call
        }
    }
}
```

The caller says `_notifier.Notify("Saved!")` — with no idea (or care) whether that means terminal output, email, or a fan-out. One call site, many behaviors: *poly-* (many) *-morph* (shapes). It composes: a `CompositeNotifier(new ConsoleNotifier(), new ConsoleNotifier())` "accidentally" works — that is the design flexing.

**Use inheritance sparingly** — the professional default is the next section. Deep hierarchies couple classes to each other (change the parent, break the children); modeling *behavior differences* with interfaces plus small implementing classes keeps every piece independently understandable and testable.

#### 13.7 Composition — the everyday alternative

**Composition** = build complex behavior by *combining* focused objects, each owning one concern ("has-a", not "is-a"):

```text
TaskManager HAS-A TaskRepository     (who owns saving/loading)
TaskManager HAS-A TaskValidator     (who owns the title rules)
TaskManager HAS-A IClock            (who owns "now")
```

`TaskManager` does not *inherit* from anything — it *uses* collaborators, each replaceable (swap JSON repository for a database one; swap real clock for frozen). The 13.5 example already did composition with `IClock`; Part IV's `TaskManager` (Chapter 17) is built by exactly this composition, with its dependencies *injected through the constructor* — the pattern's full name, **dependency injection**, arrives in Chapter 21.

The rule of thumb, stated the way professionals state it: **favor composition over inheritance** — combine small pieces; reserve inheritance for genuine "is-a" taxonomy that will stay stable.

#### 13.8 When *not* to use OOP

Honesty section. OOP is a tool for *organizing*, not a lifestyle:

- A 30-line script does not need classes — top-level statements (Chapter 4) are *the* right shape.
- Not every function needs a class: `TaskValidator` (Chapter 19) is a stateless helper — its rules are pure functions; a `static` class with static methods is the honest home for pure logic.
- Data-transfer objects (Chapter 15's `TaskItem`) are deliberately "dumb" — data plus a couple of invariants, not behavior cathedrals. Dumping 20 methods onto a data class is the mirror sin of the ball of mud.

Design principle, one sentence: **organize by responsibility** (a class per responsibility), whatever the diagram fashion of the week claims.

#### 13.9 Exercises

1. Write a `Temperature` class: private `double _celsius`; public properties `Celsius` (read-only!) and `Fahrenheit` (computed, converted); a constructor taking Celsius; methods `Add(degrees)` with a guard against cooling below -273.15 °C (absolute zero — a *physical* invariant).
2. Add an `IClock`-style contract `ILogger` with `Log(string)`, implement `ConsoleLogger`, and make your 9.10 password program accept an `ILogger` in a constructor and log attempts.
3. Why is `counter.Value = 100;` a compile error (13.4)? What would you have to do instead, and why is that *better*?
4. `TaskManager` "is-a" `List<TaskItem>`, or "has-a" `List<TaskItem>`? Argue both sides in one paragraph, then state the professional default.

<details>
<summary><b>Solutions</b></summary>

**1.**

```csharp
public sealed class Temperature
{
    private double _celsius;                       // hidden storage

    public double Celsius => _celsius;             // read-only outside
    public double Fahrenheit => _celsius * 9 / 5 + 32;   // computed, never stored

    public Temperature(double celsius)
    {
        if (celsius < -273.15)
        {
            throw new ArgumentOutOfRangeException(nameof(celsius));
        }
        _celsius = celsius;
    }

    public void Add(double degrees)
    {
        if (_celsius + degrees < -273.15)          // the physical invariant, at the door
        {
            throw new InvalidOperationException("Cannot cool below absolute zero.");
        }
        _celsius += degrees;
    }
}
```

Note: `Fahrenheit` is *derived* — storing both and keeping them in sync would be a bug factory (13.3's point 3).

**2.**

```csharp
public interface ILogger
{
    void Log(string message);
}

public sealed class ConsoleLogger : ILogger
{
    public void Log(string message) => Console.WriteLine($"[log] {message}");
}

public sealed class PasswordChecker
{
    private readonly ILogger _logger;              // composition: has-a logger

    public PasswordChecker(ILogger logger)
    {
        _logger = logger;                          // dependency injected by the caller
    }

    public bool Check(string password)
    {
        bool ok = password.Length >= 8 && password.Any(char.IsDigit);
        _logger.Log(ok ? "password accepted" : "password rejected");   // works with ANY ILogger
        return ok;
    }
}
```

**3.** Because `Value`'s setter is `private` — the class published reading (`get`) and reserved writing (`set`) to itself. To change the value you must call a *method* (`Increase()`), and the method is where rules live; direct assignment would bypass every rule. Better because "who can change this, and under what conditions" is now a designed, inspectable fact instead of a hope.

**4.** "Is-a" argument: a manager is a kind of collection of tasks, inheriting list machinery for free. "Has-a" argument: managing tasks *uses* a list as storage detail; the manager's identity is its *rules* (IDs, validation), not listness. Professional default: **has-a (composition)** — inheritance here would expose `List`'s 40+ members (including mutation methods) through the manager, breaking encapsulation (13.4) and coupling the manager's future to list internals. The `private readonly List<TaskItem> _tasks` inside `TaskManager` in Chapter 17 is exactly this decision.

</details>

---

### Chapter 14: Files, JSON, Exceptions, and Time — Beyond the Memory

> **In this chapter you will learn:** why persistence changes what a program *is*; reading and writing text files; the JSON data format read as a language; serialization and deserialization with `System.Text.Json`, with the options that matter; the philosophy of exceptions, `try`/`catch` in full, and when *not* to use them; and handling dates and times without inventing time-zone bugs. Every concept here is used directly in the repository you build in Chapter 16.
>
> **Prerequisites:** Chapters 6–13.

#### 14.1 The problem this chapter solves

Everything so far lives in **memory**: beautiful, fast — and utterly mortal. Close the program and every task evaporates. Real applications survive restarts: data must cross into the **outside world** — files, formats, clock, and failures. This chapter is the border-crossing toolkit.

#### 14.2 Text files — write, read, survive

The simplest persistence is a text file. The two workhorse methods:

```csharp
File.WriteAllText("notes.txt", "Learn problem solving.");
string text = File.ReadAllText("notes.txt");
```

Word by word:

- `File` — a .NET class devoted to file operations: one call, no ceremony (the bytes, buffers, and handles are handled for you).
- `WriteAllText(path, content)` — "write *all* of this text into the file at *path*." Creates the file, or **overwrites** it entirely — remember this when imagining data loss.
- `ReadAllText(path)` — "read the entire file into one string."
- `"notes.txt"` — a **relative path**: resolved against the program's *working directory* (where you run `dotnet run` from). Paths are the single most OS-dependent idea in programming: use forward slashes or `Path.Combine(...)`, never hand-built `C:\` + `\" + ...` string surgery.

The law of paths: **a path is external input** (Chapter 5's constraint list, now concrete). The file may be missing, locked by another program, on a full disk, or unreadable due to permissions. Professional code *expects* these — which is exactly why the next-but-one section exists.

#### 14.3 JSON — the language of data

**JSON** (**J**ava**S**cript **O**bject **N**otation) is a text format for structured data: readable by humans, parseable by every language, the lingua franca of configuration files, APIs, and (soon) your task store. The entire grammar is four ideas:

```json
{
  "id": 1,
  "title": "Learn C#",
  "done": false,
  "dueDate": null
}
```

| Construct | Symbols | Meaning |
|---|---|---|
| Object | `{ }` | A "bag of named values" — a C# object's mirror |
| Key–value pair | `"title": "Learn C#"` | Name (always a string, always quoted), colon, value |
| Array | `[ ]` | An ordered list — a C# `List`'s mirror |
| Scalars | `1`, `true`, `false`, `null`, `"text"` | A number, a boolean, absence, a string |

A list of tasks, then, is an **array of objects** — the shape our `tasks.json` will have:

```json
[
  {
    "id": 1,
    "title": "Learn C#",
    "description": "Practice decomposition",
    "status": 0,
    "createdAt": "2026-11-09T11:32:05.3193232Z",
    "dueDate": null
  }
]
```

Read it with your C# eyes: braces for objects, brackets for the list, colons for assignment, commas between members, `null` for "no due date." You now know enough JSON to read 90% of configuration files on Earth.

#### 14.4 Serialization — objects in, JSON out

**Serialization** = converting live objects into text (to store or send); **deserialization** = parsing text back into live objects. The `System.Text.Json` namespace does both, and it is built into .NET — no package needed:

```csharp
using System.Text.Json;

var options = new JsonSerializerOptions
{
    WriteIndented = true
};

string json = JsonSerializer.Serialize(task, options);
TaskItem? restored = JsonSerializer.Deserialize<TaskItem>(json, options);
```

Word by word:

- `using System.Text.Json;` — the namespace (imported implicitly in modern projects; shown because you should *know* where this lives).
- `new JsonSerializerOptions { WriteIndented = true }` — construct options; `WriteIndented = true` means "pretty-print with line breaks and indentation" — costs a few bytes, buys the ability to *read and debug your own data files* (the example above). The `{ ... }` inside `new` is an **object initializer** (10.2's array initializer's sibling): "set these properties right after constructing."
- `Serialize(task, options)` — object → JSON string. Properties become keys; values become JSON scalars.
- `Deserialize<TaskItem>(json, options)` — JSON string → `TaskItem?`. The generic parameter `<TaskItem>` says "parse into *this* type"; keys are matched to property names, and the result is `TaskItem?` — nullable, because JSON text can fail to yield an object (empty text, for example).

Two professional facts about enums and dates you will see with your own eyes in Chapter 16's real file:

- **Enums serialize as numbers** by default: `TaskStatus.InProgress` becomes `1`. Human-readable alternative: an option (`JsonStringEnumConverter`) that writes `"InProgress"` — mentioned for recognition; the number form is smaller and perfectly stable for machine use.
- **`DateTime` serializes to ISO 8601**: `2026-11-09T11:32:05Z` — the `T` separates date and time; trailing `Z` means UTC (next section). One unambiguous, machine-sortable format, worldwide.

#### 14.5 Exceptions — handling the unpredictable professionally

An **exception** is .NET's mechanism for *exceptional failures*: situations outside the normal contract of the code — missing file, corrupted JSON, full disk — where "return a default and pretend" would be dishonest. When one is **thrown**, normal execution stops and the runtime searches for a handler:

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

Anatomy:

- `try { ... }` — "run these statements *under observation*; failures here will not kill the program."
- `catch (FileNotFoundException)` — "if a *file-missing* failure occurred, run this block instead of crashing." First matching `catch` wins; order **specific → general** (as here: `FileNotFoundException` *is an* `IOException`, so it must come first, or the general clause would swallow it — CS pattern hygiene).
- `catch (IOException error)` — a general disk-family failure, and the clause *captures the exception object* as `error`, whose `.Message` property carries the human-readable explanation.
- Unlisted exception types (e.g., out of memory) propagate onward — `catch` is a filter, not a net.

The **philosophy**, which matters more than the syntax:

1. **Exceptions are for exceptional conditions** — genuinely unpredictable failures. They are *not* a validation mechanism: expected, recoverable situations get `TryParse` and conditions (6.11, 7.4), not exceptions. A user typing letters into an age prompt is *expected*; a save file corrupted by a power cut is *exceptional*.
2. **Handle where you can decide.** Catch at the layer that knows what to *do* about it: the repository layer (Chapter 16) decides "corrupted file → start empty with a message"; a menu loop does not know what corrupted JSON even means.
3. **Never catch silently** — `catch { }` with an empty body hides failure and manufactures species-3 logic bugs out of real errors (12.2). Even the minimum is `catch (Exception error) { Console.Error.WriteLine(error.Message); }`.
4. **Finally** — the third clause you will meet: `finally { ... }` runs *no matter what* (success, handled failure, unhandled failure) — for cleanup like closing connections. Recognize it; use it when you have resources to release.

#### 14.6 Date and time — the quietly dangerous type

Dates look trivial and are not: time zones, daylight-saving jumps, leap years, and "what did the user *mean* by 2026-11-09?" all bite real projects. Two rules keep you safe in this guide and in most applications:

**Rule 1: store and compute in UTC.**

```csharp
DateTime createdAt = DateTime.UtcNow;     // the one true clock: Coordinated Universal Time
```

`DateTime.UtcNow` is the machine's instant in UTC — unambiguous, sortable, timezone-free. `DateTime.Now` (local wall-clock time) is for *displaying* to a user, never for *storing* — storing local time is how "due dates move when the server's country changes" incidents happen. (Notice `Z` in the serialized timestamps of 14.4: our stored times are UTC, always.)

**Rule 2: treat user-entered dates as calendar dates; convert deliberately.** A user typing `2026-12-01` means "that calendar day" — we keep it as a plain date (our `ReadOptionalDate` helper in Chapter 18 does exactly `date.Date`, which zeroes the time-of-day) and do not pretend it is a UTC instant. What matters is *deciding and documenting* which kind every `DateTime` in your program is — mixing the two silently is the actual bug, far more than any API misuse.

Parse and format with the tools from 6.9/6.11 — same family, now complete:

```csharp
if (DateTime.TryParse("2026-12-01", out DateTime date))   // the TryParse law (6.11) holds
{
    Console.WriteLine(date.ToString("yyyy-MM-dd"));         // 2026-12-01 — our canonical format
}
```

#### 14.7 Exercises

1. Write a program that saves your three favorite numbers as JSON (serialize a `List<int>`) and reads them back. Inspect the file in your editor — what does `WriteIndented` change, exactly?
2. Wrap exercise 1's read in a `try`/`catch` that survives: (a) a missing file — print "no data yet" and continue; (b) garbage text in the file — print the parse failure and continue. Which exception types catch each?
3. Serialize a small class with a `bool`, an `int`, a `string`, a `DateTime`, and an enum property. Predict the JSON before looking. Which two values surprise a JSON newcomer?
4. Explain in two sentences why the Task Manager will store `CreatedAt` as `DateTime.UtcNow` but let users enter `DueDate` as a plain date (no time).

<details>
<summary><b>Solutions</b></summary>

**1.**

```csharp
using System.Text.Json;

List<int> favorites = new() { 7, 42, 100 };
var options = new JsonSerializerOptions { WriteIndented = true };

File.WriteAllText("favorites.json", JsonSerializer.Serialize(favorites, options));

List<int>? loaded = JsonSerializer.Deserialize<List<int>>(File.ReadAllText("favorites.json"), options);
loaded?.ForEach(n => Console.WriteLine(n));      // 7, 42, 100
```

`WriteIndented` adds line breaks + two-space indentation per level — `[\n  7,\n  42,\n  100\n]` instead of `[7,42,100]`. Same data, human-readable versus compact.

**2.**

```csharp
try
{
    string text = File.ReadAllText("favorites.json");
    List<int>? loaded = JsonSerializer.Deserialize<List<int>>(text);
    Console.WriteLine(loaded != null ? loaded.Count.ToString() : "empty data");
}
catch (FileNotFoundException)          // case (a): specific first
{
    Console.WriteLine("No data yet.");
}
catch (JsonException error)          // case (b): parse family — malformed text
{
    Console.WriteLine($"Saved data is corrupted: {error.Message}");
}
```

(a) is `FileNotFoundException`; (b) is `JsonException` (`IOException` remains a third, worth catching in production disk code).

**3.** Predicted and actual: `true` stays `true` (JSON has real booleans), `7` stays `7`, text becomes `"..."`, the date becomes an ISO-8601 string like `"2026-11-09T11:32:05Z"`, and — the newcomer's surprise — the **enum becomes a number** (`0`/`1`/`2`), because that is `System.Text.Json`'s default for enums (14.4). The other surprise is usually that everything is one stringified shape: property names match exactly, casing included.

**4.** `CreatedAt` is a fact about the *system* ("when was this record born") — a UTC instant is unambiguous and comparable across servers and timezones, so it is stored as `DateTime.UtcNow`. A `DueDate` is a fact about the *user's calendar* ("finish by December 1") — a day, not an instant — so it is captured as a plain date. Different kinds of time, different representations, *documented* — which is the entire rule.

</details>

---

## Part IV — The Project: Building Task Master

Everything so far was preparation. In Part IV you build a real application — **Task Master** — applying every tool from Parts I–III in its natural place. Five chapters, five layers, one program. Every file is explained statement by statement, every design choice is justified, and every command you type is given to you. **Do not skip ahead**: each chapter ends with a checkpoint, and the next chapter builds on your working code.

> **Verification note:** every line of code in Part IV was compiled and executed with .NET 10 before being written here, and the transcript in Chapter 18 is real output. If your program differs from the guide, *read the compiler message* (Chapter 4.8) — the compiler is always more precise than any tutorial.

---

### Chapter 15: Task Master Part 1 — Design and the Domain Model

> **In this chapter you will learn:** how the 7-step process (Chapter 5) produces the design of a real application; how responsibilities become classes; how to scaffold the project; the domain model — the `TaskStatus` enum and the `TaskItem` class — explained property by property; and you will meet — and defeat — your first genuine cross-library name collision.
>
> **Builds on:** all previous chapters.

#### 15.1 From requirement to design — applying the process

Recall the precise sentence from Chapter 1.7:

> "Allow a user to create a task with a non-empty title, an optional description, and an optional due date; list, search, update, and delete tasks; persist all data to a local JSON file; and recover gracefully from a missing or corrupted file."

Run it through the seven steps (Chapter 5):

| Step | Result for Task Master |
|---|---|
| 1. Restate | The sentence above |
| 2. Examples | Add "Buy milk" → created, `#1` shown; empty title → refused; search `c#` → finds `Learn C#` (case-insensitive); delete missing ID → "Task not found" |
| 3. Edge cases | Empty/whitespace title; no tasks (empty state); missing `tasks.json`; corrupted JSON; ID that does not exist; duplicate titles (allowed for now — documented); past due dates (allowed) |
| 4. Pseudocode | The menu-loop sketch of 5.5 |
| 5. Data | One `TaskItem` shape; many of them in order → `List<TaskItem>`; lookup by ID → scan with `FirstOrDefault` (Chapter 11 says fine at this scale); status limited to three values → enum |
| 6. Smallest version | Models + repository + add + list (this chapter and the next two); search/update/delete follow |
| 7. Test & improve | Chapter 18's scripted session, then Chapter 19's unit tests |

Now the architectural question: *what kinds of things does this program need?* Answer by listing **responsibilities** — one kind of change = one component:

| Component | Sole responsibility | Chapter |
|---|---|---|
| `TaskItem` | Represent one task's data | this chapter |
| `TaskStatus` | Define the three legal states | this chapter |
| `TaskRepository` | Save and load tasks (files, JSON, failures) | 16 |
| `TaskManager` | Own task rules and state changes (IDs, validation, search) | 17 |
| `InputReader` | Read and validate console input | 18 |
| `Program` | The user interface: menu, display, coordination | 18 |

This is a small **layered architecture** — the shape of nearly every serious business application:

```text
        ┌───────────────────────────────┐
        │  Program (UI layer)          │  talks to the human
        ├───────────────────────────────┤
        │  TaskManager (service layer)  │  owns the RULES
        ├───────────────────────────────┤
        │  TaskRepository (persistence) │  owns STORAGE
        ├───────────────────────────────┤
        │  TaskItem / TaskStatus        │  the DOMAIN — shared vocabulary
        └───────────────────────────────┘
```

Each arrow points one way, downward. The UI never touches files; the repository never prints menus; the domain knows nothing about either. Why this discipline pays (the same list from 9.9, at application scale):

- Replace the console UI with a web API → `TaskManager` untouched (Chapter 21 does exactly this).
- Replace JSON with a database → only `TaskRepository` changes.
- Test the rules → construct a `TaskManager` with a fake repository; no terminal needed (Chapter 19).

#### 15.2 Scaffold the project

In your terminal:

```bash
dotnet new console -n TaskMaster
cd TaskMaster
mkdir Models Services
```

Word by word: `dotnet new console -n TaskMaster` — you know this one (4.4); `mkdir Models Services` — create two folders *in one command* (`mkdir` takes multiple names): `Models` for the domain types, `Services` for the collaborating classes. Folders are optional in C# — but they *are* your architecture made visible; readers should find things where the diagram says.

The target structure:

```text
TaskMaster/
├── Models/
│   ├── TaskItem.cs          <- this chapter
│   └── TaskStatus.cs        <- this chapter
├── Services/
│   ├── InputReader.cs       <- Chapter 18
│   ├── TaskRepository.cs    <- Chapter 16
│   ├── TaskValidator.cs    <- Chapter 19
│   └── TaskManager.cs       <- Chapter 17
├── Program.cs               <- Chapter 18
└── TaskMaster.csproj        <- created for you (4.5)
```

Run the empty project once to confirm the foundation (`dotnet run` — prints "Hello, World!"), then delete the contents of `Program.cs` — we will write it properly in Chapter 18. (An empty file compiles fine for now.)

#### 15.3 The `TaskStatus` enum — three states, by construction

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

Word by word:

- `namespace TaskMaster.Models;` — declare that everything in this file belongs to the named group `TaskMaster.Models` (the trailing `;` form is the C# 10 **file-scoped namespace**: everything below belongs to it, no extra braces). Namespaces prevent name collisions across a big codebase and mirror your folders — `Models` folder, `TaskMaster.Models` namespace.
- `public` — visible to the other folders of the project (and the world); the domain vocabulary must be public, or nothing can speak it.
- `enum` — "a **fixed set of named values**": exactly the tool for a rule like *status may only be Todo, InProgress, or Done*.
- `TaskStatus` — the type's name.
- `Todo, InProgress, Done` — the three legal members. Under the hood each is a number (`Todo` = 0, `InProgress` = 1, `Done` = 2 — which is why Chapter 14's JSON stores `0`/`1`/`2`), but you write words; the compiler enforces the vocabulary.

What the enum *buys* you — the difference between "a status is a string" and "a status is a type":

```csharp
TaskStatus s = TaskStatus.InProgress;   // legal
TaskStatus t = (TaskStatus) 99;          // possible via cast — the escape hatch, deliberately ugly
string wrong = "In Progres";             // a typo compiles fine if statuses were strings
```

`task.Status = "In Progres"` — with `string` statuses — would *compile* and break silently. With the enum, misspelling `TaskStatus.InProgress` is a **compile error**, and "invent a new status" requires a deliberate cast. Rules move from "hope" to "the type system enforces it" — encapsulation of vocabulary (13.4).

#### 15.4 The `TaskItem` class — the domain, line by line

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

The header, word by word:

- `namespace TaskMaster.Models;` — same group as the enum; the domain types live together.
- `public` — shared vocabulary of the application.
- `sealed` — "no class may inherit from me" (13.6). A data model is a leaf: complete in itself. `sealed` states the decision and lets the compiler optimize small things.
- `class TaskItem` — the blueprint of one task (13.2).

The properties, one by one — each chosen deliberately:

- **`public int Id { get; set; }`** — the task's unique number. `get; set;` = a read-write property (13.3): the repository (deserialization) and the manager (ID assignment) write it; the UI reads it. The *uniqueness rule* is the manager's job (Chapter 17), not the type's — a plain `int` here is honest: the class stores, the service enforces.
- **`public string Title { get; set; } = string.Empty;`** — the required name of the task. The part after `=` is an **initializer**: "every new `TaskItem` starts with an empty-string title." Why it matters: without it, a freshly constructed `TaskItem` has `Title == null`, and the first `.Title.Trim()` somewhere crashes with a `NullReferenceException` — *the* classic C# failure. Defaulting to `""` (and validation to enforce non-empty at the door, 18/19) makes null-titles a non-event. This is a rule made *structural* (13.4).
- **`public string Description { get; set; } = string.Empty;`** — same pattern; optional text, never null.
- **`public TaskStatus Status { get; set; } = TaskStatus.Todo;`** — the state, typed as the enum: new tasks begin as `Todo` *by construction*. An impossible starting state is a bug that cannot happen.
- **`public DateTime CreatedAt { get; set; } = DateTime.UtcNow;`** — when the task was born. **A subtle and important detail:** `DateTime.UtcNow` here is evaluated *once per construction* — each `new TaskItem()` captures its own birth instant (14.6's rule 1: stored time is UTC — see it appear in the `tasks.json` of 16.3).
- **`public DateTime? DueDate { get; set; }`** — the optional deadline. The nullable annotation (6.10) is the whole point: `null` *is* "no due date chosen" — a designed absence, checked with `is`/`HasValue`/`?.`/`??` wherever used.

Why so simple — no methods, no constructor? Because `TaskItem` is a **data model**: its job is to *carry* the domain's shape (a judgement call of 13.8 — data classes stay plain; behavior lives in the service that owns the rules). You will see in Chapter 16 that this plainness is exactly what makes JSON persistence a one-liner.

#### 15.5 Your first real-world collision — `TaskStatus` is taken

Now the promised battle scar. Type Chapter 17's `TaskManager.cs` now, or simply *plan* to — the moment it uses `TaskStatus` after `using TaskMaster.Models;`, the build may fail with:

```text
error CS0104: 'TaskStatus' is an ambiguous reference between
'TaskMaster.Models.TaskStatus' and 'System.Threading.Tasks.TaskStatus'
```

Decode it with 4.8's method (and Appendix C):

- **CS0104** — "two different types share this name, and I cannot guess which one you mean."
- The conflict: the .NET class library *itself* contains `System.Threading.Tasks.TaskStatus` (a low-level enum describing parallel `Task` states — unrelated to to-do lists). Modern templates import `System.Threading.Tasks` for you (`ImplicitUsings`, 4.5). So the name `TaskStatus` now means *two* types at once: yours, and theirs.

The fix — one line, placed among your `using` directives in any file that touches the type:

```csharp
using TaskStatus = TaskMaster.Models.TaskStatus;
```

Word by word: this is a **using alias** — "in *this file*, whenever I write `TaskStatus`, I mean `TaskMaster.Models.TaskStatus`, full stop." The compiler is told your intent explicitly and the ambiguity is gone. Add it to the two files that use the type (`TaskManager.cs`, `Program.cs`).

Two lessons, worth more than the fix:

1. **Name collisions with the standard library happen to everyone** — a library as huge as .NET contains almost every short domain word. When the compiler complains, read it: it names *both* candidates, and the remedy (qualify or alias) is mechanical.
2. **This is why 12.3's procedure exists.** A dabbler sees CS0104, panics, renames their enum in three files, and breaks nothing *visibly*. You read the message, understood both candidates, and chose the smallest precise fix.

(The alternative fix — renaming our enum to `TaskItemStatus` — is equally valid; the alias keeps the natural domain name, which is why professional codebases often prefer it.)

#### 15.6 Checkpoint — what you must have before Chapter 16

```text
□ TaskMaster project created and dotnet run prints Hello, World! (or nothing — Program.cs empty)
□ Models/TaskStatus.cs created — enum with Todo, InProgress, Done
□ Models/TaskItem.cs created — six properties exactly as listed
□ dotnet build succeeds with zero errors
```

Run `dotnet build` — success output ends with `0 Error(s)`. If not: read the message, check Appendix C for the code, fix, rebuild. The discipline starts now.

---

### Chapter 16: Task Master Part 2 — Persistence, the Repository

> **In this chapter you will learn:** what a repository is and why the whole application talks to storage through one class; `TaskRepository` line by line and word by word — including the exception-handling strategy of 14.5 applied for real; what your `tasks.json` file will look like (actual verified output); and the design decisions that make swapping JSON for a database a one-file change.
>
> **Builds on:** Chapter 15 checkpoint.

#### 16.1 What a repository is — and why you want one

A **repository** is the class whose entire job is: *take domain objects, put them somewhere permanent; take permanent storage, give back domain objects*. Everything else in the application stays innocent of files, JSON, disks, and failures.

What the rest of the app sees — two operations:

```text
List<TaskItem> Load()      → "give me all saved tasks"
void   Save(List<TaskItem> tasks)   → "here are all tasks; persist them"
```

What only the repository sees: paths, `File` calls, JSON options, missing files, corrupted files, locked files. One door, guarded once (13.4 at application scale) — and Chapter 21's database upgrade becomes *this file only*.

#### 16.2 The code — `Services/TaskRepository.cs`

Create the file with exactly this content:

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

#### 16.3 Every line, explained

**The header and fields:**

- `using System.Text.Json;` — import the serialization namespace (14.4).
- `using TaskMaster.Models;` — see `TaskItem` (no alias needed here: this file never says the word `TaskStatus`).
- `namespace TaskMaster.Services;` — this class belongs to the services layer's namespace.
- `public sealed class TaskRepository` — public (the manager and `Program` must construct it); `sealed` (a leaf, not a base for inheritance — 15.4's reasoning again).
- **`private readonly string _filePath;`** — *where* the tasks live: a path given from outside, stored privately. `private` — no other class even knows a file exists (the whole point of this chapter). `readonly` — "assignable **only in the constructor**, frozen afterwards" (13.5's `_clock` pattern): the repository cannot accidentally point itself at a different file mid-run. `_camelCase` — the field convention from the front matter.
- **`private readonly JsonSerializerOptions _jsonOptions = new() { WriteIndented = true };`** — the pretty-print options from 14.4, built **once** and reused: `new()` with empty brackets is C# 9's target-typed construction (10.3) — the type is known from the field's declared type; the `{ ... }` is the object initializer (14.4). Storing it as a field is a deliberate micro-optimization: options objects do non-trivial setup, and rebuilding them per save is waste — build once, reuse forever.

**The constructor:**

- `public TaskRepository(string filePath)` — the parameter *is* the design decision "which file" handed in from outside. `Program` (18.2) will construct it as `new TaskRepository("tasks.json")` — relative path, resolved against the working directory (14.2). Passing the path in (rather than hardcoding) means tests can point at a temporary folder, and the file location becomes configuration, not law.
- `_filePath = filePath;` — the standard one-line constructor: capture what was given. Every `new TaskRepository(...)` now has a path before it can work — invalid states unconstructible (13.3's point 4).

**`Load()` — read everything, fail safely:**

- `public List<TaskItem> Load()` — returns the whole list; `List` (not `IReadOnlyList`) deliberately: the manager *owns* mutation of the returned data; the repository's job ends at the door.
- `if (!File.Exists(_filePath))` — the **missing file is not an error**: first run of the app ever? Then there are no tasks yet — `return new List<TaskItem>();` — an empty list. (Chapter 5's edge case, met with the *friendliest possible* behavior: a brand-new user starts clean, not in an error dialog.)
- `try` — the disk and the file's *contents* are both outside our control (14.5: genuinely exceptional territory): wrap the dangerous operations.
- `string json = File.ReadAllText(_filePath);` — 14.2's method: whole file into one string.
- `return JsonSerializer.Deserialize<List<TaskItem>>(json, _jsonOptions) ?? new List<TaskItem>();` — 14.4's deserialization, with the generic type spelled `List<TaskItem>` ("parse into a list of tasks"), and the `??` (6.10) catching the "text parsed to `null`" case (e.g., the literal text `null` in the file) — degrade to empty rather than hand back a null list.
- `catch (JsonException)` — the file exists but is not valid JSON (user hand-edited it; an editor crashed mid-save): say so in plain language, **start with an empty list**. A corrupted file must not mean data-loss panic or a crash — the app degrades and continues. Specific catch first (14.5's ordering rule).
- `catch (IOException error)` — the disk family of failures (locked file, permissions, drive gone): report the exception's own `.Message` (14.5's captured variable), degrade to empty. Note *what is not caught*: anything else (out of memory, etc.) still propagates — this method catches exactly the failures it has a policy for, no more (the honesty of 14.5's rule 3).

**`Save()` — write everything:**

- `string json = JsonSerializer.Serialize(tasks, _jsonOptions);` — 14.4: live list → pretty JSON text.
- `File.WriteAllText(_filePath, json);` — 14.2: text → whole file (create or overwrite). Simple and correct for a single-user console app. (A production system with concurrent writers would need atomic-save tricks — noted for Chapter 21, deliberately not built now: smallest working version first, 5.7.)

#### 16.4 What your saved file looks like — verified

After Chapter 18's UI exists and you add one task, `tasks.json` will contain *exactly* this shape (real output from the verified build — annotated here):

```json
[
  {
    "Id": 1,
    "Title": "Learn C#",
    "Description": "Practice decomposition",
    "Status": 0,
    "CreatedAt": "2026-11-09T11:32:05.3193232Z",
    "DueDate": null
  }
]
```

Read it with 14.3's grammar: an array containing one object; six keys mirroring the six properties (casing preserved); `"Status": 0` — `Todo`, serialized as its number (14.4's enum fact); `"CreatedAt"` — an ISO-8601 UTC instant ending in `Z` (14.6's rule 1, visible in the wild); `"DueDate": null` — 15.4's designed absence, serialized honestly. **You can now open your application's data and read it like a document.** That is what `WriteIndented` bought.

#### 16.5 The design decisions, restated as policy

1. **The file is external** — expected to be missing, corrupted, or locked; every path through `Load` returns *a usable list* no matter what the disk did.
2. **Errors become messages, never crashes** — 14.5's "handle where you can decide": this layer decides "degrade to empty and inform."
3. **The format is human-readable** — debuggable data is a feature.
4. **The path is injected** — tests and future config decide where data lives.
5. **`Save` overwrites wholesale** — one writer, one file, no partial states; correct at this scale, revisited at 21.3's scale.

#### 16.6 Checkpoint

```text
□ Services/TaskRepository.cs created exactly as above
□ dotnet build → 0 Error(s)
```

(Nothing user-visible yet — the repository is the engine; the wheels come in the next two chapters.)

---

### Chapter 17: Task Master Part 3 — Business Logic, the Manager Service

> **In this chapter you will learn:** the service layer's role; `TaskManager` line by line — constructor wiring, listing, adding (validation + ID generation + object initializers), deleting, updating, and searching; how each method applies a principle you already own (guards, `FirstOrDefault`, LINQ, `IReadOnlyList`); and the two invariants this class exists to enforce.
>
> **Builds on:** Chapters 15–16 checkpoints.

#### 17.1 The brain of the application

The repository knows storage; the UI knows humans; between them, **`TaskManager` knows the rules**: what makes a task legal, how IDs are born, what "search" means, what happens when a change is made. Nothing else in the application may change task state — one guarded door per rule (13.4, at the scale that matters most).

Its public surface — the API the UI will call in Chapter 18:

```text
GetAll()                    → all tasks, sorted by ID
Add(title, description, due) → a new TaskItem (or throws: invalid title)
Delete(id)                  → true if deleted, false if not found
UpdateStatus(id, status)     → true if updated, false if not found
Search(text)                 → matching tasks, sorted by ID
```

Note the shape: **queries return data; commands return success/failure booleans** — the `TryParse` pattern of 6.11, applied to domain operations. "Task not found" is an *expected* outcome, reported with a `bool`, not an exception (14.5's rule 1 — users get politeness).

#### 17.2 The code — `Services/TaskManager.cs`

Create the file (the alias line from 15.5 included — expect CS0104 without it):

```csharp
using TaskMaster.Models;
using TaskStatus = TaskMaster.Models.TaskStatus;

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

#### 17.3 Every method, explained

**The header, fields, and constructor:**

- `using TaskMaster.Models;` — import the domain types.
- `using TaskStatus = TaskMaster.Models.TaskStatus;` — the 15.5 alias: this file *says* `TaskStatus` (in `UpdateStatus`), so it must state which one it means, or meet CS0104 again.
- `private readonly TaskRepository _repository;` — **composition** (13.7): the manager *has-a* repository, injected from outside. `readonly` — the manager is wired once and never rewires itself.
- `private readonly List<TaskItem> _tasks;` — the in-memory working set: the current truth of the application, loaded once, mutated here, saved on every change.
- `public TaskManager(TaskRepository repository)` — the constructor *receives its dependency* (13.5's `IClock` pattern, now for real storage): `_repository = repository;` then `_tasks = _repository.Load();` — **the application's state is born loaded**: from the first instruction after construction, saved tasks are present and consistent.
- Two invariants this class quietly enforces forever (Chapter 20 names them formally): *every task ID is unique and positive*; *every task title is non-empty after trimming*.

**`GetAll()` — the safe read:**

- Returns **`IReadOnlyList<TaskItem>`** — the interface of 10.7's table: callers can `foreach` and index-read, but *cannot* add/remove — `tasks.Add(...)` from outside is a compile error. The manager's list is protected by its type, not by hope (13.4 again — this is what "make invalid operations unrepresentable" looks like in an API).
- The body is one LINQ chain (10.10): `_tasks.OrderBy(task => task.Id).ToList()` — "the tasks, sorted ascending by ID, materialized." Sorting a *copy* (10.9) preserves storage order while guaranteeing stable display order — display is a view, storage is a fact.

**`Add(...)` — the careful creation.** Four movements, in order:

1. **Validate.** `if (string.IsNullOrWhiteSpace(title)) throw new ArgumentException("A task title is required.", nameof(title));` — the guard clause (9.8): the one rule the manager was born to enforce. `ArgumentException` because a *programmer* contract was violated ("`Add` requires a title" — the UI should have collected one; a violated precondition is an exception, 14.5). `nameof(title)` — the parameter name as text, refactor-safe (9.8).
2. **Generate the ID.**

   ```csharp
   int nextId = _tasks.Count == 0
       ? 1
       : _tasks.Max(task => task.Id) + 1;
   ```

   The `? :` is the **conditional (ternary) operator** — new here; read it as a two-branch value: `condition ? valueIfTrue : valueIfFalse`. Empty list → start at `1`; otherwise → **max existing ID + 1** (10.10's `Max` with a lambda). Why max+1 and not count+1? Deleted tasks would make `Count + 1` collide with a survivor: add 3 tasks, delete #2, and `Count + 1` = 3 — but #3 exists. Max+1 never collides (given only this method creates IDs — the invariant, held by construction).
3. **Build.** `TaskItem task = new() { ... };` — target-typed `new` (10.3) plus **object initializer** (14.4): construct and set properties in one statement. `title.Trim()` and `description.Trim()` — 6.8's cleanup at the door: stored data is *clean* data. `DueDate = dueDate` — the nullable date passes through as-is: `null` is "no due date" (15.4). `Status` and `CreatedAt` are untouched — their initializers (15.4) already chose `Todo` and now.
4. **Commit.** `_tasks.Add(task);` — in-memory truth updated; `_repository.Save(_tasks);` — disk updated *immediately*: every completed command is durable the moment it succeeds (crash → nothing unsaved; 16.5's policy). `return task;` — hand the created object (with its ID) to the caller for confirmation messages.

**`Delete(int id)` — the polite refusal:**

- `TaskItem? task = _tasks.FirstOrDefault(item => item.Id == id);` — 10.10's safe lookup: first task whose ID matches, or `null` if none. The `TaskItem?` declaration is the compiler *knowing* absence is possible (6.10).
- `if (task is null) return false;` — pattern-matched null check (6.10): "not found" is an expected outcome → `false`, no exception, no crash (17.1's contract).
- `_tasks.Remove(task);` — remove **the found object** (by reference), not "index `id`": IDs and indexes are different numbers (10.2), a distinction this line quietly respects.
- `_repository.Save(_tasks); return true;` — persist, report success.

**`UpdateStatus(int id, TaskStatus status)`:** the same lookup-refuse-persist skeleton — find or `false`; then `task.Status = status;` — safe by type: `status` *is* a `TaskStatus`, one of the three legal members (15.3); an illegal value could only arrive via a deliberate cast (15.5's escape hatch). Save, return `true`.

**`Search(string text)`:**

- `IReadOnlyList<TaskItem>` — again a copy-as-readonly-view: searching must never mutate.
- The LINQ chain, read as the sentence it is: *take the tasks; **where** the title contains the text — case-insensitively (6.8's `OrdinalIgnoreCase` — the same word means the same thing regardless of caps) — **or** the description does; order by ID; materialize.* One statement = the entire feature (10.8's generalized scan, expressed declaratively — and 11.5's decision that `O(n)` scan is right at this scale, revisited by 22.2's challenge 15).
- `Contains` with two arguments — the professional overload that takes the whole-string-as-typed and the comparison mode: no lowercasing copies, no locale surprises (6.8).

#### 17.4 The pattern beneath the code

Look back at `Delete` and `UpdateStatus` — they share a skeleton, and it is a *pattern* worth naming because you will write it hundreds of times:

```text
LOOK UP (FirstOrDefault)  →  REFUSE (is null → false)  →  MUTATE  →  PERSIST  →  REPORT
```

Lookup-or-refuse separates "you gave me a bad ID" (expected, `false`) from genuine failures (exceptional, exceptions). Persist-on-every-change keeps memory and disk from drifting apart. Report honestly lets the UI speak accurately. Every command in Part IV follows it.

#### 17.5 Checkpoint

```text
□ Services/TaskManager.cs created exactly as above (alias included)
□ dotnet build → 0 Error(s)
```

Still nothing to *run* — one chapter left before the program speaks. Everything you have built so far is the machinery; Chapter 18 gives it a face.

---

### Chapter 18: Task Master Part 4 — The User Interface

> **In this chapter you will learn:** `InputReader` — the input toolkit — method by method; `Program.cs` — the menu loop and every UI handler, line by line; how one keystroke travels through all four layers and back; how to run and test Task Master with a scripted checklist; and the real, verified transcript of a complete session.
>
> **Builds on:** Chapters 15–17 checkpoints. This chapter completes the working application.

#### 18.1 The face of the application

The UI layer makes one promise to the rest of the system: *humans are handled here, and only here*. It reads keystrokes, validates them into clean data, calls manager methods, and turns results into words on a screen. It owns **no rules** (if a rule could be bypassed by clever typing, the UI is not the place to enforce it — the manager's guards are), and **no storage** (it never touches a file). Recall the layer diagram of 15.1: `Program` sits on top and talks *only* to `TaskManager` and `InputReader`.

#### 18.2 The code — `Services/InputReader.cs`

Create the file:

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

Word by word:

- `public static class InputReader` — a **static class**: a class that can never be instantiated (`new InputReader()` is a compile error); all members are `static`. The honest home for stateless helpers (13.8's rule) — input reading has no data of its own, only behavior.
- Every method is `public static` — callable as `InputReader.ReadRequiredText(...)` directly, no object needed (9.2's `static`, now fully used).
- **`ReadRequiredText`** — you already know it line by line: it *is* Chapter 7.5's method, unchanged. What was a teaching example is now shipped code — that is how this guide works: nothing was decoration.
- **`ReadOptionalText`** — the lenient sibling: ask once, trim (6.8), return — empty string is a legal answer ("no description"). The defensive line `Console.ReadLine()?.Trim() ?? string.Empty` (7.5's operator chain) guarantees a real string out.
- **`ReadInt`** — the 7.4 pattern, looping: `int.TryParse` (6.11's law for user numbers) → return on success, else explain and re-ask. Note `Console.ReadLine()` is passed *directly* as `TryParse`'s argument — expressions nest freely (9.2).
- **`ReadOptionalDate`** — the most interesting logic in the file, read it top to bottom: read a line; trim; **if empty → return `null`** (the *designed* absence of 15.4 — pressing Enter means "no due date"); **else `DateTime.TryParse`** (6.11's pattern for dates) → on success return `date.Date` — `.Date` **zeroes the time-of-day**: a due date is a calendar day (14.6's rule 2), so `2026-12-01 18:45` becomes exactly `2026-12-01 00:00`; on failure explain and re-ask.

Why this class exists at all (and not raw `ReadLine` calls scattered in `Program`): *one rule, one home* (9.9). When you later decide required text must also be at least 3 characters, you change one method — not five call sites.

#### 18.3 The code — `Program.cs`

Replace the file's contents with:

```csharp
using TaskMaster.Models;
using TaskMaster.Services;
using TaskStatus = TaskMaster.Models.TaskStatus;

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
        TaskStatus status = ReadStatus();

        bool updated = manager.UpdateStatus(id, status);
        Console.WriteLine(updated ? "Status updated." : "Task not found.");
    }

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

    private static void DeleteTask(TaskManager manager)
    {
        int id = InputReader.ReadInt("Task ID to delete: ");
        bool deleted = manager.Delete(id);
        Console.WriteLine(deleted ? "Task deleted." : "Task not found.");
    }
}
```

#### 18.4 Every part, explained

**Header and `Main` — the wiring:**

- The three `using`s: domain, services, and the 15.5 alias (this file says `TaskStatus` in `ReadStatus`).
- `public static class Program` — static: a coordinator with no state of its own; all its methods are static (13.8's rule).
- **`public static void Main()`** — the **entry point** (4.5's "real shape"): execution begins on this exact method signature — the runtime looks for it by name.
- **`TaskRepository repository = new("tasks.json");`** — construct the persistence layer, *choosing the data location* here and only here (16.3's decision, made in one line: target-typed `new`, one string argument).
- **`TaskManager manager = new(repository);`** — construct the brain, *handing it its dependency* (17.3's constructor: the manager now loads saved tasks). Two lines, and the entire architecture of 15.1 is wired: `Program` → `TaskManager` → `TaskRepository` → disk.
- **`while (true)`** — the application loop: show menu → read choice → dispatch → repeat forever, until a `return` in the Exit case ends `Main` (8.4's intentional infinite loop).
- `ShowMenu();` — call the helper (below).
- `string choice = Console.ReadLine()?.Trim() ?? string.Empty;` — read the menu choice with the full defensive chain (7.5): trimmed, never null.
- `Console.WriteLine();` — one blank line for breathing room before the action's output (small kindnesses are part of UI work).
- **`switch (choice)`** — 8.3's construct in its natural habitat: one value, several known alternatives, a `default` for the unknown ("Unknown menu choice." — never silence, never a crash). Each `case` calls one handler method and `break`s.
- `case "0": Console.WriteLine("Goodbye."); return;` — **`return` inside the switch exits `Main` itself**, which ends the program — the only exit from the loop. Every other case *break*s and falls to the loop's bottom.

**`ShowMenu` — pure presentation:** eight `WriteLine`s and one `Write` — the menu is a string constant's worth of pixels; the `Write` at the end (no newline) parks the cursor after "Choose an option: " so the user's typing lands on the same line (7.2). `private` — only `Program` calls it (13.3's naming law).

**`AddTask` — collect, delegate, confirm:**

```csharp
string title       = InputReader.ReadRequiredText("Title: ");          // required → loop until real
string description = InputReader.ReadOptionalText("Description: ");   // optional → empty is legal
DateTime? dueDate  = InputReader.ReadOptionalDate("Due date (optional): "); // optional date → null is legal
```

Three inputs, three *deliberately chosen* input policies. Then `TaskItem task = manager.Add(title, description, dueDate);` — hand clean data to the rules-owner and take back the created task. Then confirm with its real ID: `Console.WriteLine($"Task #{task.Id} created.");` — interpolation (6.8) over the object the manager returned: the UI never invented an ID, it *reported* one.

**`ListTasks` — the display contract:**

- Takes **`IReadOnlyList<TaskItem>`** — works identically for "all tasks" and "search results" (17.3's readonly view), which is why `SearchTasks` can reuse this method verbatim — one display, many sources.
- `if (tasks.Count == 0) { Console.WriteLine("No tasks found."); return; }` — **the empty state is designed**, not accidental: no tasks → friendly sentence, and `return` ends the method (9.3's early return; Chapter 5's "no silence" rule).
- `foreach (TaskItem task in tasks)` — 8.7's loop over the sorted view.
- `string due = task.DueDate?.ToString("yyyy-MM-dd") ?? "none";` — the compact null-handling idiom (6.10) doing real work: optional date → either the canonical `yyyy-MM-dd` (6.9) or the word `none`. Note what is *not* here: an `if (DueDate.HasValue)` ladder — the `?.` + `??` chain says it in one line.
- `$"#{task.Id} [{task.Status}] {task.Title} | Due: {due}"` — the task in one line: `#1 [Todo] Learn C# | Due: 2026-12-01` (an enum in interpolation prints its *name* — the words, not the number; JSON is the exception, not the rule).
- The indented second line prints the description *only when it exists* — conditional presentation (8.2's `if` with one statement).

**`SearchTasks`:** read required text (the same policy as titles — a blank search is refused), call `manager.Search(text)` (17.3's case-insensitive rule), and **hand the results to `ListTasks`** — search results are just a list; the display code does not care where lists come from. Two lines of glue, because both ends were designed for reuse.

**`ChangeStatus`:** `ReadInt` for the ID (looping until numeric — but *note*: a numeric-but-nonexistent ID is the manager's polite `false`, not the input reader's business — each layer refuses what it can judge); `ReadStatus()` (below) for the new state; then `bool updated = manager.UpdateStatus(id, status);` and the ternary report `Console.WriteLine(updated ? "Status updated." : "Task not found.");` — the `?:` from 17.3, mapping a boolean to a human sentence.

**`ReadStatus`** — the *fixed* version (the deliberately simpler "v1 with a flaw" and the full story of fixing it is Chapter 19's opening lesson): a `while (true)` loop printing the three legal choices, `ReadInt` to read the number, a `switch` on the integer returning the matching `TaskStatus` member — and for `default`, an explanation and another loop, **forever, not an exception**. Expected invalid input is normal interaction (7.3's law, mechanically obeyed). Compare 8.3's structure — it is the same switch, with `return` instead of `break`, because returning *is* the exit.

**`DeleteTask`:** the same lookup-and-report shape as `ChangeStatus` — read ID, call the manager, map the boolean to "Task deleted." / "Task not found.". Notice there is *no* "Are you sure?" — challenge 6 of 22.2 adds it; you know exactly which method would grow.

#### 18.5 The complete runtime flow — one keystroke, four layers

Press `1` at the menu and follow the journey (the 15.1 diagram, animated):

```text
1. Main's while loop: ShowMenu prints the six options; ReadLine returns "1".
2. switch matches case "1" → AddTask(manager).
3. AddTask → InputReader.ReadRequiredText("Title: ")   (UI asks; input layer validates)
4. AddTask → InputReader.ReadOptionalText / ReadOptionalDate (collect the rest)
5. AddTask → manager.Add(title, description, due)     (crossing into the SERVICE layer)
6. Add validates the rule (guard), generates ID (max+1), builds TaskItem (object initializer)
7. Add → _repository.Save(_tasks)                      (crossing into PERSISTENCE)
8. Save serializes to JSON and writes tasks.json       (crossing into the OUTSIDE WORLD)
9. Add returns the TaskItem → AddTask prints "Task #3 created."
10. switch breaks → loop prints a blank line → ShowMenu → the next keystroke...
```

Ten steps, four layers, one keystroke. Read the trace once more after your first real run — every line of Part IV is inside that paragraph.

#### 18.6 Run it — `dotnet run`

From the `TaskMaster` folder:

```bash
dotnet run
```

The menu appears. Test this exact sequence (the numbers echo 17.1's contracts — and this sequence was executed against the verified build):

1. Choose `1`; title `Learn C#`; description `Practice problem decomposition`; due date `2026-12-01` → `Task #1 created.`
2. Choose `1`; press Enter alone at the title → `A value is required.` — asks again: type `Read a book`; Enter through description and due date → `Task #2 created.`
3. Choose `2` → both tasks listed, `#1` first with `[Todo]` and its due date.
4. Choose `4`; ID `1`; status `2` → `Status updated.`
5. Choose `3`; search `c#` → the title task found (lowercase search matched `C#` — 17.3's `OrdinalIgnoreCase` working).
6. Choose `5`; ID `2` → `Task deleted.`
7. Choose `2` → only task `#1` remains, `[InProgress]`.
8. Choose `0` → `Goodbye.`
9. **Run the program again** → the menu lists the survivor immediately (persistence!); and, with a text editor, **corrupt `tasks.json`** (delete a bracket), run again → the friendly recovery message, empty start (16.3's `JsonException` branch, live).

The verified transcript of steps 1, 3, 4, and 5 (your punctuation may differ slightly):

```text
=== Task Master ===
1. Add task
2. List tasks
3. Search tasks
4. Change task status
5. Delete task
0. Exit
Choose an option: Title: Description: Due date (optional): Task #1 created.
...
Choose an option: #1 [Todo] Learn C# | Due: 2026-12-01
    Practice decomposition
...
Choose an option: Search text: #1 [InProgress] Learn C# | Due: 2026-12-01
    Practice decomposition
```

(The prompts appear on one line in the transcript because scripted input answers instantly; interactively each waits for your typing.)

#### 18.7 Checkpoint — the application is alive

```text
□ dotnet run shows the menu
□ Task created, listed, searched, status-changed, deleted — all six menu paths exercised
□ tasks.json exists and opens in an editor as readable JSON (16.4's shape)
□ Restart → data survives; corrupted file → friendly recovery, no crash
```

**Stand back and see what you built.** Five focused files; every rule has one owner; every failure has a friendly answer; the data survives you. This is not a toy exercise — it is a correct miniature of how professional applications are structured.

---

### Chapter 19: Task Master Part 5 — Quality: Fix, Validate, Test, Refactor

> **In this chapter you will learn:** how to judge and fix a deliberate design flaw (exception vs re-asking, the decision you will face weekly as a developer); how to extract a validator so rules get a permanent, testable home; how to create a real xUnit test project for Task Master and write meaningful tests for the rules; and the safe refactoring cycle that lets you change structure without breaking behavior.
>
> **Builds on:** the working application from Chapter 18.

#### 19.1 The flaw in version 1 — an exception as a menu answer

Here is a version of status selection you will find in many tutorials (and in earlier drafts of this guide's source material). It is *temptingly compact* — it uses a **switch expression** (a C# 8 form: cases produce *values*):

```csharp
// flawed design — read on for why
TaskStatus status = statusChoice switch
{
    1 => TaskStatus.Todo,
    2 => TaskStatus.InProgress,
    3 => TaskStatus.Done,
    _ => throw new ArgumentException("Invalid status choice.")
};
```

Word by word: `statusChoice switch { 1 => ..., 2 => ..., }` — "compare `statusChoice`; the whole expression *becomes* the value of the matching arm" (`_` = "anything else", the arm equivalent of `default`). It compiles. It even works — for correct users.

**And it is wrong.** A user pressing `7` at that prompt is not an *exceptional* situation; it is a *Tuesday*. The typing of invalid menu numbers is not merely *possible*, it is *certain* — Chapter 7.3's whole point. Throwing an exception there violates 14.5's first rule (exceptions are for exceptional conditions), and in a console app without a top-level handler it **terminates the program**, losing the user's session and mood:

```text
Unhandled exception. System.ArgumentException: Invalid status choice.
   at TaskMaster.Program.ChangeStatus(...)
...
```

**The judgment, stated as a reusable rule:**

> Expected, recoverable situations → loops, booleans, re-asking.
> Broken program invariants and impossible states → exceptions.

Put the user's mistake on the left of that line and the programmer's mistake on the right, and you have the rule 80% of API design errors.

**The fix** — exactly the `ReadStatus` method that Chapter 18 shipped: replace the throwing arm with a loop that explains and re-asks (`"Choose 1, 2, or 3."`) until a legal value arrives. If you built Chapter 18 as written, you already own the fixed version; if your build still contains the flawed one, replace the `ChangeStatus` status-selection with 18.4's `ReadStatus` now, re-run the scripted session of 18.6, and press `7` at the status prompt — the program answers politely instead of dying.

This is a problem-solving improvement in the purest sense (Chapter 1 through 20 in one line): *the program now treats expected invalid input as normal interaction rather than as a crash*.

#### 19.2 Extract the validator — rules get a home

Chapter 17's `Add` enforces "title required." Suppose the rules grow (they always do): required, **and** at most 120 characters, **and** (challenge 1 of 22.2) unique among existing titles. Strings of `if`s inside `Add` will bloat the method and mix *validation* with *creation*. The 9.9 move: extract a validator, give every rule a permanent, single-purpose home.

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

Design decisions, read closely:

- **`static class`** — pure logic, no state (13.8): the honest home for rules that are functions.
- **Returns a `string`, not a `bool`** — richer than yes/no: `string.Empty` ("") means *valid* (and what a deliberate convention that is: "no error message" *is* the success value); any non-empty result *is* the human-readable error. One method answers both "is it valid?" and "if not, why?" — and the *why* flows straight to the UI:
- **It never prints, never throws** — presentation (telling the human) and policy enforcement (calling an exception) are not this method's job. It is a *pure question about data*, which is exactly what makes it testable in the next section — no console capture needed (12.6's dream setup).

Wire it into `TaskManager.Add`, replacing the inline guard (17.2):

```csharp
string error = TaskValidator.ValidateTitle(title);

if (error.Length > 0)
{
    throw new ArgumentException(error, nameof(title));
}
```

Read the flow: ask the validator; if it produced an error *text*, that text becomes the exception's message (the manager still throws — because by the time control reaches `Add`, the UI contract "collect a valid title" was violated — the *programmer* error, 14.5; the validator itself stays presentation-free and test-friendly).

#### 19.3 The test project — verifying the rules for life

Chapter 12 taught AAA on a small example; now make it real for Task Master. From the *solution root* (the folder containing the `TaskMaster` folder):

```bash
dotnet new xunit -n TaskMaster.Tests
dotnet add TaskMaster.Tests reference TaskMaster
```

(The second command's exact meaning from 12.6: the tests project gains a *project reference* — it can now `using TaskMaster.Services;` and see your public classes.)

Replace the generated `UnitTest1.cs` with `TaskValidatorTests.cs`:

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

    [Fact]
    public void VeryLongTitle_ReturnsAnError()
    {
        string error = TaskValidator.ValidateTitle(new string('x', 121));

        Assert.Equal("A title cannot exceed 120 characters.", error);
    }
}
```

Line by line where it matters:

- `using TaskMaster.Services;` — the project reference at work (19.3's wiring made this legal).
- `new string('x', 121)` — a *constructed* edge: the `string` constructor repeats a character N times; 121 is **max + 1**, the classic boundary test (12.7's "minimum and maximum" — the fence post, probed one past the post).
- Each test is self-contained AAA with arrange-act on one line — the scenario is trivial, so the ceremony is minimal; the **names** carry the documentation (12.6's naming law).
- All three assert on the *exact error strings* — strong tests (they pin the user-facing contract), with the known cost: rewording a message turns tests red. Deliberate trade: here the messages *are* part of the product.

Run:

```bash
dotnet test
```

```text
Passed! - Failed: 0, Passed: 3
```

Now the regression discipline (12.8): every bug you find from now on becomes a `[Fact]` in this file, and the green bar grows only ever greener.

**Testing the manager too — the testability payoff arrives.** Because `TaskManager` takes a `TaskRepository` (17.3), tests can point one at a throwaway path:

```csharp
public class TaskManagerTests
{
    [Fact]
    public void Add_EmptyTitle_Throws()
    {
        TaskManager manager = new(new TaskRepository(Path.Combine(Path.GetTempPath(), $"t{Guid.NewGuid()}.json")));

        Assert.Throws<ArgumentException>(() => manager.Add("   ", "", null));
    }

    [Fact]
    public void Add_ThenGetAll_ReturnsTheNewTask()
    {
        TaskManager manager = new(new TaskRepository(Path.Combine(Path.GetTempPath(), $"t{Guid.NewGuid()}.json")));

        TaskItem created = manager.Add("Learn C#", "deep work", null);

        Assert.Equal(1, created.Id);
        Assert.Single(manager.GetAll());
        Assert.Equal("Learn C#", manager.GetAll()[0].Title);
    }
}
```

- `Path.GetTempPath()` + `Guid.NewGuid()` — every test gets its **own throwaway file**: tests never share state, never read *your* real tasks, and clean up is trivial (challenge: make them delete their file — a `finally` from 14.5 fits perfectly).
- `Assert.Throws<ArgumentException>(() => manager.Add(...))` — 12.9's exercise, now shipped: the guard (17.2) is under permanent surveillance.
- `Assert.Single(...)` — asserts *exactly one* element; `Assert.Equal(1, created.Id)` — the ID-generation rule (17.3) pinned forever.
- **Notice what is absent**: no console, no keystrokes, no manual anything — the rules are exercised directly. That is the architectural promise of 15.1 kept: *test the rules without simulating the keyboard.*

#### 19.4 Refactoring — changing structure without changing behavior

**Refactoring** = reorganizing code so it is clearer/simpler, *with behavior provably unchanged*. The provably part needs the green bar. The cycle (12.3's spirit, applied to structure):

```text
1. Run all tests            → green (the safety net is deployed)
2. Make ONE structural change  (extract a method / rename / move a class / delete duplication)
3. Build                    → 0 errors (syntax intact)
4. Run all tests            → still green? behavior is preserved.
5. Inspect the diff         → is the new shape actually better? if not, revert.
6. Commit (if using git)    → one refactoring = one commit, revertible.
7. Repeat.
```

The law inside the loop: **never refactor and redesign behavior in the same change.** The moment "while I am in here, let me also change what Delete does on missing IDs" joins a "pure rename" commit, the tests go red for *two* reasons at once and neither is diagnosable. One structural change, one commit, always.

Candidate refactorings for your current Task Master (each a 10-minute exercise, in increasing ambition):

1. **Rename** `ListTasks` → `DisplayTasks` (does the name say what it does?).
2. **Extract** the blank-line-printing into a small `Pause()` method — remove the duplication.
3. **Move** `ReadStatus`'s three `WriteLine`s into a `ShowStatusOptions()` — presentation separated from selection.
4. **Consolidate** `ChangeStatus` and `DeleteTask`'s shared lookup-and-report shape — feel the 17.4 pattern wanting a helper; consider whether the abstraction is *actually* better (sometimes near-duplication is honest duplication: 9.7's judgment).

#### 19.5 Where you now stand

The application is complete **and** it has a quality apparatus: validation has a home, the rules have tests, the design has layers, and you own the two disciplines (debug procedure, refactor cycle) that keep software alive past its first week. Part V takes you deliberately *beyond* this project — the same thinking at bigger scales.

```text
□ TaskValidator created and wired into Add
□ Test project created, referenced, 3+ validator tests and 2+ manager tests green
□ dotnet test → Passed! — Failed: 0, Passed: 5 (or more)
□ One refactoring performed through the full cycle, tests green before and after
```

---

## Part V — Toward Mastery

The application works and has tests. Part V widens the lens: advanced problem-solving techniques (with verified implementations), how console programs grow into production applications, and finally a concrete, honest roadmap from where you now stand to genuine mastery.

---

### Chapter 20: Advanced Problem-Solving Techniques

> **In this chapter you will learn:** recursion and when it is beautiful or dangerous; divide and conquer; greedy algorithms with a proven example; dynamic programming and memoization; backtracking with a complete working generator; invariants — the correctness tool you already use implicitly; immutability; and asynchronous programming with a precise mental model of `async`/`await`. Every code sample here was compiled and executed before being written into this guide.
>
> **Prerequisites:** the full Parts I–IV journey.

#### 20.1 Recursion — a method that calls itself

A **recursive method** solves a problem by calling itself on a *smaller* version of the same problem:

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

Trace `Factorial(5)` to *see* recursion — the calls stack up (10.6's LIFO), then unwind:

```text
Factorial(5)
= 5 * Factorial(4)
= 5 * (4 * Factorial(3))
= 5 * (4 * (3 * Factorial(2)))
= 5 * (4 * (3 * (2 * Factorial(1))))
= 5 * (4 * (3 * (2 * 1)))        <- the BASE CASE answers: 1
= 5 * (4 * (3 * 2))
= 5 * (4 * 6)
= 5 * 24
= 120                             <- verified output
```

Every recursive solution needs exactly three things — check for all three or it is broken:

1. **A base case** — a smallest problem answered directly (`n <= 1` → return 1). No base case = infinite recursion = `StackOverflowException` (each pending call consumes stack memory; the stack is finite — the runtime kills you politely).
2. **Progress toward the base case** — every call must be *strictly smaller* (`n - 1`). `Factorial(n)` calling `Factorial(n)` makes no progress.
3. **A correct combination** — the answer assembled from the smaller answer (`n *` the rest).

Where recursion shines: problems that are *naturally* self-similar — trees (file systems!), nested structures, divide-and-conquer (next section). Where it backfires: simple iteration (a loop computing factorial is clearer and cheaper in C#) and unbounded depth. Professional rule: **use recursion when the data or definition is recursive; use loops when the work is merely repetitive.**

#### 20.2 Divide and conquer — split, solve, combine

**Divide and conquer**: split the problem into independent smaller copies of itself, solve those, combine the results. You have already used it without ceremony — binary search (11.4) *is* divide and conquer with a single survivor half; merge sort splits a list in half recursively, sorts each half, and merges; and the Task Master's own architecture is the same idea at design scale — the *problem* "manage tasks" was divided (15.1) into persistence, rules, UI — each independently solved, then *combined* by wiring (18.4). Divide and conquer is Chapter 5's "decompose" step, promoted to an algorithmic strategy.

#### 20.3 Greedy algorithms — the locally best choice

A **greedy algorithm** makes the best-looking choice *at each step* and never reconsiders. It is simple and fast — and *sometimes* provably optimal, which depends entirely on the problem's mathematical structure. The classic case where greedy is *correct*: choosing the maximum number of non-overlapping events (meeting rooms, TV shows, tasks with start/end times):

```csharp
static int MaxNonOverlappingEvents((int Start, int End)[] events)
{
    var sorted = events.OrderBy(e => e.End).ToArray();   // greedy key: EARLIEST ENDING first
    int count = 0;
    int lastEnd = int.MinValue;

    foreach (var e in sorted)
    {
        if (e.Start >= lastEnd)      // compatible with everything chosen so far?
        {
            count++;
            lastEnd = e.End;
        }
    }

    return count;
}
```

Line by line:

- `(int Start, int End)` — a **tuple**: a small unnamed bundle of values (C# 7); `e.Start`/`e.End` access the named parts — perfect for "a pair of numbers traveling together" without inventing a class.
- `OrderBy(e => e.End)` — **the greedy choice**: sort by *ending* time. Why earliest-end? Choosing what frees the room soonest leaves maximum room for the future — the insight that makes the greedy correct here (provable; this is a textbook result).
- The loop: take an event if it starts at or after the last chosen event's end; otherwise skip silently.

Verified run: `MaxNonOverlappingEvents(new[] { (1,4), (2,3), (5,7), (6,8) })` → `2` — sort by end: `(2,3), (1,4), (5,7), (6,8)`; take `(2,3)` (lastEnd=3); `(1,4)` starts at 1 < 3, skip; take `(5,7)` (lastEnd=7); `(6,8)` starts at 6 < 7, skip. Two events.

The **warning label**: greedy works here because of structure (formally: the problem has the "greedy-choice property"); on other problems — say, picking coins to make change with awkward denominations — the greedy choice can miss the optimum entirely. Before trusting a greedy: try to break it with small examples, and prefer a proven pattern or a proof when the stakes are real.

#### 20.4 Dynamic programming — solve each subproblem once

**Dynamic programming (DP)** applies when a problem splits into *overlapping* subproblems — the same smaller questions asked again and again. Naive recursion then recomputes exponentially; DP solves each subproblem **once** and reuses the answer.

The canonical demonstration — naive Fibonacci, where `Fib(40)` takes *seconds* because `Fib(3)` is recomputed millions of times:

```csharp
static long Fib(int n)
{
    if (n <= 2)
    {
        return 1;
    }
    return Fib(n - 1) + Fib(n - 2);          // O(2^n): overlapping subproblems re-solved forever
}

static long FibMemo(int n, Dictionary<int, long> cache)     // memoized: same recursion, cached
{
    if (n <= 2)
    {
        return 1;
    }
    if (cache.TryGetValue(n, out long cached))             // 10.4's safe lookup
    {
        return cached;
    }
    long result = FibMemo(n - 1, cache) + FibMemo(n - 2, cache);
    cache[n] = result;                                     // remember — each n solved exactly once
    return result;
}
```

Verified: `Fib(10)` → `55`; `FibMemo(40, new Dictionary<int, long>())` → `102,334,155` — *instantly*, versus naive `Fib(40)` recomputing ~10^11 redundant calls. The dictionary — "have I solved this before?" — is the entire trick: **cache the answer to every solved subproblem**. The name for the cache is *memoization*; the discipline (recognize overlap → store → reuse) is dynamic programming, and it powers everything from shortest paths to diff tools to spell-checkers.

**When to reach for DP:** the problem's answer for `n` is expressible through answers for smaller inputs (the *recurrence*), and the same smaller inputs recur. Those two signs — recurrence + overlap — are the tell; finding the recurrence is the actual work.

#### 20.5 Backtracking — choose, explore, un-choose

**Backtracking** systematically explores *choices*: commit to one, recurse deeper, and — if the branch fails — *undo the choice* and try the next. It is how programs solve puzzles with constraints: permutations, combinations, Sudoku, path-finding. The complete, verified generator of all orderings of `{1, 2, 3}`:

```csharp
static void Permute(int[] items, int start, List<int[]> results)
{
    if (start == items.Length - 1)                    // base case: one position left → a full ordering
    {
        results.Add((int[])items.Clone());           // save a COPY (6.4: arrays are references!)
        return;
    }

    for (int i = start; i < items.Length; i++)
    {
        (items[start], items[i]) = (items[i], items[start]);   // CHOOSE: swap candidate into place
        Permute(items, start + 1, results);                    // EXPLORE: fix the rest recursively
        (items[start], items[i]) = (items[i], items[start]);   // UN-CHOOSE: swap back — backtrack!
    }
}
```

Read the loop's three beats — **choose, explore, un-choose** — because that is the entire pattern:

1. **Choose**: the tuple-assignment `(a, b) = (b, a)` swaps two positions in one statement (a C# 7 nicety) — "let position `start` hold candidate `i`."
2. **Explore**: recurse to arrange the remainder.
3. **Un-choose**: the *mirror swap* restores the array exactly — crucial, or siblings of the search would inherit each other's mess. Verified: `Permute(new[]{1,2,3}, 0, results)` yields `6` orderings (3! = 6).

The deep structure (spot the recursion law of 20.1): base case = "nothing left to arrange"; progress = `start + 1`; combine = the saved copy. Backtracking = recursion + choices + undo; when you next meet a puzzle (place N queens, fill a grid), the shape will be these three beats again.

#### 20.6 Invariants — facts that must stay true

An **invariant** is a statement that must remain true *throughout* execution — the professional's correctness compass. You have been writing them since Chapter 17; now see them named:

| Invariant (Task Master) | Enforced where |
|---|---|
| Every task ID is unique and positive | only `Add` creates IDs (max+1) — 17.3 |
| Every task title is non-empty after trimming | `Add`'s guard / `TaskValidator` — 17.3, 19.2 |
| Every status is one of the three enum members | the `TaskStatus` type — 15.3 |
| Memory list and `tasks.json` hold the same data | save-immediately-after-every-change — 17.3 |
| Valid indexes are `0` to `length - 1` | loops with `<` everywhere — 8.10 |

In classic algorithms, invariants explain *why they work*: in each iteration of selection sort, "positions before index `i` hold the smallest values in final order"; in binary search, "if the target exists, it lies within `[low, high]`" (11.4's table keeps holding it — that is the proof the algorithm is correct).

**Use invariants actively:** when you write a loop, write a comment stating what is true on every pass ("// invariant: largest so far is in `champion`") — 12.2's species-3 bugs *are* broken invariants, and a stated invariant is checkable (even assertable, 12.5) while a vague one is decoration.

#### 20.7 Immutability — values that cannot change

**Immutable** data cannot be modified after creation — instead of changing, you *create a new value*: no method mutates the old one, ever. You have met it twice already — `string` (6.8: every operation returns a *new* string) and `IReadOnlyList<T>` (17.3: a view that cannot be mutated). Why professionals reach for it deliberately:

- **No surprise edits.** A value passed to a method cannot come back altered (aliasing bugs, 6.4's two-arrows picture — impossible).
- **Safe sharing.** Immutable data can be shared across threads without locks (Chapter 20's async section touches threads).
- **Reasonable history.** "The task as it was at creation" stays available — *because nothing can retroactively edit it*.

Applied to Task Master: rather than `task.Status = newStatus;` mutating the object, an immutable design would build a *new* task value with the changed status (`record` types, C# 9, are the language's one-line tool for this: `TaskItem updated = task with { Status = TaskStatus.Done };`). Our mutable model was the right beginner choice — simpler and idiomatic for a single-user tool — but know the trade exists: mutation is convenient; immutability is predictable. Distributed and functional systems pay the small overhead happily.

#### 20.8 Async — waiting without freezing

Some operations are *slow in the outside world*: files on busy disks, network calls, database queries. A program that **blocks** (freezes its thread) while waiting is wasting the machine — and, in a UI, visibly freezing. **Asynchronous programming** lets one thread start a slow operation, go do other work, and be *resumed* when the result is ready:

```csharp
static async Task<string> ReadFileAsync(string path)
{
    return await File.ReadAllTextAsync(path);
}
```

Word by word — the three-piece incantation:

- **`async`** — the method *modifier*: "this method may `await` things; it will be compiled into a resumable state machine, not a simple sequence."
- **`Task<string>`** — the return type: not a string, but *"a promise of a string, later*" — a task that will, in the future, hold the result (or the failure). Callers `await` the task.
- **`await`** — the operator: "pause *this method* — not the whole program — until this task finishes; then and only then, continue with the result." The thread is *released* during the pause.

The pair is what makes it work: `async` defines *where* pausing is possible; `await` marks *where* a pause happens. Calling it: `string text = await ReadFileAsync("tasks.json");` — reads naturally, behaves asynchronously.

Two honest caveats, both lived professional wisdom:

- **Do not add `async` because it is fashionable.** Use it when the operation is *naturally* asynchronous — file, network, database, timers. CPU math is not that; `async` buys nothing there.
- **Single-user console Task Master does not need it.** The win arrives with concurrency: a web server (Chapter 21) awaiting 200 disk reads *at once* on a small thread pool — that is where one line of `await` saves a hundred threads.

#### 20.9 Exercises

1. Write `static int Sum(int[] numbers, int index)` recursively — the sum of items from `index` on. Identify the base case, the progress, and the combination before running it.
2. Your coin denominations are `{1, 4, 5}` and you must make `8` with the fewest coins. What does the greedy (largest coin first) yield, and what is the true optimum? Which technique from this chapter finds it?
3. Hand-trace `Permute` on `{1, 2}` and write the two saved orderings in the order the generator saves them.
4. State two invariants of your own Task Master build not listed in 20.6.
5. Convert `ReadFileAsync`'s caller to asynchronous: write `static async Task Main(string[] args)` that reads a file with `await` and prints it.

<details>
<summary><b>Solutions</b></summary>

**1.**

```csharp
static int Sum(int[] numbers, int index)
{
    if (index == numbers.Length)      // base: no items left → sum of nothing is 0
    {
        return 0;
    }
    return numbers[index] + Sum(numbers, index + 1);   // combine: this item + rest
}
```

Base = empty range answers `0`; progress = `index + 1`; combination = addition.

**2.** Greedy: 5 + 1 + 1 + 1 = four coins. Optimum: **4 + 4 = two coins**. Greedy fails (the structure of 5 dominating 4 is a trap), and the technique that finds the true optimum is **dynamic programming**: `minCoins(n) = 1 + min over each coin c ≤ n of minCoins(n - c)`, with `minCoins(0) = 0` — overlapping subproblems, memoize. (This exercise is 20.3's warning label made concrete.)

**3.** `Permute({1,2}, 0)`: `start=0`, loop `i=0`: swap(0,0) (no change), recurse `start=1` → base case → save `{1,2}`; un-swap. Then `i=1`: swap(0,1) → `{2,1}`, recurse → save `{2,1}`; un-swap. Saved order: `{1,2}`, then `{2,1}` — and each saved *only once* because the base case copies (6.4/20.5's `Clone`).

**4.** Examples (check your own): "the menu always displays exactly the legal operations"; "`Search` never adds, removes, or modifies tasks — results are a copy"; "every repository method returns a usable list, even on failure" (16.5's policy — an invariant *of a failure path*).

**5.**

```csharp
public static class Program
{
    public static async Task Main()                     // async Main: allowed since C# 7.1
    {
        string text = await ReadFileAsync("tasks.json");
        Console.WriteLine(text);
    }

    static async Task<string> ReadFileAsync(string path)
    {
        return await File.ReadAllTextAsync(path);
    }
}
```

`Main` may itself be `async Task` — the runtime awaits the whole program's completion. (If `tasks.json` is missing this crashes — exercise: wrap with 14.5's try/catch and print a friendly line.)

</details>

---

### Chapter 21: From Console Program to Production Application

> **In this chapter you will learn:** what "production" actually means; how Task Master's layers let it grow into a web API without rewriting the rules; when to graduate from JSON to a database; dependency injection as a formal pattern; logging, security, and deployment thinking — and, most importantly, which parts of your hard-won design survive every one of these steps.
>
> **Prerequisites:** Chapters 15–20.

#### 21.1 What "production" means

A **production** application is one that serves real users who are not you, on machines you cannot watch, at hours you are asleep. The definition changes the requirements: failures must be *observed* (logging), configuration must be *external* (not recompiled to change a path), data must be *protected* (backups, permissions), updates must be *safe*, and multiple requests may arrive *simultaneously*. None of this is new problem solving — it is Chapter 5's "constraints" list, extended past the terminal.

The good news, and the thesis of this chapter: **your layered design (15.1) was built for exactly this day.**

#### 21.2 The web API version — same brain, new face

A web application exposes operations over HTTP: browsers, phones, other servers call endpoints such as:

```text
GET    /tasks            → list tasks (the HTTP verb for "read")
POST   /tasks            → create a task ("submit/create")
PUT    /tasks/{id}/status → update status ("replace")
DELETE /tasks/{id}       → delete ("remove")
```

How small is the change? With ASP.NET Core's **minimal APIs** (the modern, low-ceremony style), a functioning API is genuinely a few lines *plus the Task Master you already wrote*:

```csharp
var builder = WebApplication.CreateBuilder(args);
builder.Services.AddSingleton(new TaskRepository("tasks.json"));
builder.Services.AddSingleton<TaskManager>();

var app = builder.Build();

app.MapGet("/tasks", () => Results.Json(app.Services.GetRequiredService<TaskManager>().GetAll()));

app.Run();
```

Read the crucial line: `...TaskManager().GetAll()` — **the exact method you wrote in Chapter 17**, called the exact same way the menu called it. `TaskManager` does not know (or care) whether its caller is a switch statement or an HTTP router — that is the 15.1 promise kept, in public. The domain rules (validation, IDs, search semantics) apply *unchanged* to web clients: the UI was replaced; the brain was not.

(The `builder.Services.AddSingleton` lines are dependency injection — the pattern formalized in the next section, used here to hand the API's components the same instances the console's `Main` constructed by hand in 18.4.)

#### 21.3 Database persistence — when JSON stops being enough

JSON-in-one-file is *correct* for a single-user local tool — and *insufficient* the moment any of these appear:

| Requirement | Why a file cannot deliver |
|---|---|
| Multiple users/writers at once | Two simultaneous `Save`s interleave; last write wins, data lost |
| Queries ("all tasks due this week, by priority") | Linear scans, no indexes (11.2) |
| Transactions ("move a task AND log it — both or neither") | Files have no atomic multi-write story |
| Larger-than-memory data | `ReadAllText` loads everything |
| Backups, access control, integrity constraints | You would rebuild a DB badly, feature by feature |

The graduation is deliberately painless *because of the repository*: a `SqliteTaskRepository` (or PostgreSQL variant) implements the same two methods — `Load` and `Save` become `SELECT` and `INSERT/UPDATE/DELETE` — and **only `Program`'s one construction line changes** (`new TaskRepository("tasks.json")` → `new SqliteTaskRepository(connectionString)`). `TaskManager` was never allowed to know storage details (16.1's whole point), so it needs zero edits. One class swaps; the application lives.

**Before** introducing a database, write the data model and invariants down (Chapter 5 discipline): a database does not fix unclear requirements — it *preserves* them, faster, with more users.

#### 21.4 Dependency injection — wiring as an explicit discipline

You have done **dependency injection (DI)** by hand since 17.3: `TaskManager` receives its `TaskRepository` through the constructor. The formal pattern just names the benefits and adds a place to do it at scale:

- **Injected** = "dependencies are provided from outside, not constructed inside." `TaskManager` does not `new` its repository (18.4's `Main` does the wiring — a role called the *composition root*).
- Why it matters — each a chapter you already lived:
  - **Testability** (19.3): tests injected throwaway repositories; no real files touched.
  - **Replaceability** (21.3): swap JSON for SQLite at one construction site.
  - **Configurability** (21.2): the web host registers "one `TaskManager` for the whole app" and injects it into every endpoint consistently.
- The container (21.2's `builder.Services`) is only a **mechanized composition root**: a dictionary of "when someone needs X, here is how to build it." Nothing conceptual is new — 17.3's constructor *was* the pattern.

One professional naming gift: `AddSingleton` says "one shared instance lives for the whole application lifetime" — exactly right for our state-holding `TaskManager`; `AddScoped` (per web request) and `AddTransient` (per use) are the other lifetimes you will meet in web projects.

#### 21.5 Logging — the flight recorder

When production misbehaves, you cannot attach a debugger to a user's laptop at 2 a.m. **Logging** is the discipline of recording important events as they happen, so yesterday's failure is diagnosable today:

```csharp
_logger.LogInformation("Task {Id} created", task.Id);
_logger.LogError(error, "Could not read the task file");
```

(Using Microsoft's `ILogger` — but any logging library implements the same idea: timestamped, leveled, structured records.) What to record — the events that answer "what happened?" in a diagnosis:

- application start / stop (was it even running?)
- task created / updated / deleted (with *which* IDs — the *what*)
- **persistence failures** (16.3's catches — currently they print; in production they log and continue)
- unexpected exceptions (at a top-level handler — the 14.5 catch-of-last-resort)

And the two laws: logs must never contain **secrets** (passwords, tokens, personal data — a log file is the most exfiltrated artifact in software) and must be **useful, not noisy** (a log line per keystroke is a haystack; one line per *significant event* is a flight recorder).

#### 21.6 Security principles — the standing orders

Console apps feel safe; web apps *are* an open port. The checklist that applies to anything you ship:

1. **Validate at trust boundaries** (7.6's five questions — now for HTTP bodies and headers, not just keystrokes): *all* external data is hostile until validated; the good news is the *domain rules* already refuse nonsense — they just need to be behind every entry point (this is why validation lives in the manager/validator, not the menu: 19.2's placement, now security-relevant).
2. **Never store secrets in source code** — API keys, connection strings, passwords. Externalize to configuration/environment (21.4's injection), and never commit them (git history is forever).
3. **Least privilege** — the app's OS account and DB account get exactly the permissions they need, nothing more.
4. **Treat dependencies as external input** — outdated packages are the standard route in (update them: `dotnet list package --outdated`).
5. **Protect the data at rest** — file permissions, backups, encryption where warranted (a task list knows its users' lives).

#### 21.7 Deployment thinking — questions before launch

The pre-flight list, which is Chapter 5's constraint-gathering aimed at servers:

- **Configuration**: where does the data path / connection string come from? (Environment variables / config files — *not* recompilation.)
- **Data location & durability**: where does the JSON or database live? What happens when the disk fills (14.2's reality, at scale)?
- **Observability**: where do logs go, and who reads them? How will we *know* the app is down (health checks) — before a user tweets?
- **Updates**: how do we ship v2 without dropping the v1 data file? (Migrations — a schema versioning discipline.)
- **Backups and recovery**: when the machine dies, how much data is lost, and who restores it? Rehearse the restore, not just the backup.
- **Dependency failure**: what does the app do when the database/network/disk is briefly gone? (Degrade politely — 16.3's pattern, at system scale.)

None of these are "deployment questions" in the end; they are **problem-solving questions** — inputs, rules, constraints, and success measures (Chapter 1) — applied to the problem called "running software for strangers."

#### 21.8 What survives — the point of the whole guide

The console app becomes a web API: **the rules survive untouched** (17.3's `TaskManager`). The JSON becomes a database: **the contracts survive** (16.1's `Load`/`Save`). The UI becomes a website: **the domain survives** (15.3/15.4). Frameworks, storage engines, and interfaces are *replaceable shells around a core of clear thinking* — and the core of clear thinking is what Parts I–III built, and what you now own.

---

### Chapter 22: The Mastery Roadmap

> **In this chapter you will learn:** where you truly stand now; what to learn and build at each of the four levels beyond beginner; fifteen progressive challenges that grow Task Master into a portfolio piece; and the mastery questions that tell you whether you can trust your own understanding.

#### 22.1 The four levels — with "you are ready when" tests

**Level 1 — Absolute beginner → *you are here or beyond it now*.**
Learn: terminal commands; the entry point; variables and types; operators; conditions; loops; methods; strings; input validation — Chapters 4–9 of this guide.
Build: a greeting program; a temperature converter; a calculator; a number-guessing game (5.10); a small quiz.
*You are ready to move on when* you can write a program that reads input, validates it, branches on it, loops over a list, and splits into named methods — **without looking anything up except method names**.

**Level 2 — Practical problem solver → *you are entering this level*.**
Learn: collections in depth; search and sorting; complexity; file I/O; JSON; exceptions; debugging procedure; unit testing — Chapters 10–14, 19.
Build: a contact book; an expense tracker; an inventory manager; a text-file analyzer; **Task Master challenge 1–8 below**.
*You are ready when* you can take a problem you have never seen, produce the five-part analysis and pseudocode, implement it with tests, and defend the data-structure choice aloud.

**Level 3 — Application developer.**
Learn: classes/interfaces deeply; layered architecture; DI; async; a real database (start with SQLite via EF Core or Dapper); HTTP and APIs.
Build: the REST API for tasks (21.2 — do it); a notes app with full-text search; a library management system; a booking system; a personal finance tracker.
*You are ready when* your projects start with a design document (15.1), carry tests from day one, and you can add a feature to a 2,000-line codebase without fear.

**Level 4 — Advanced engineer.**
Learn: algorithm analysis beyond Big O basics; concurrency and thread safety; caching; distributed system patterns (retries, idempotency); observability; security in depth; performance profiling; deployment and operations (containers, CI/CD).
Build: a multi-user task service with accounts and authorization; a background job processor; an event-driven notification service; a search service; **one** production-style portfolio application deployed publicly, monitored, and documented.
*You are ready when* you can reason about what two simultaneous users do to your design (17.4's booleans were single-user — what are they now?), and when "it works on my machine" no longer appears in your vocabulary.

#### 22.2 The fifteen progressive Task Master challenges

Complete them **in order** — each builds on the last, and each trains a specific muscle. For *every* challenge, run the full Chapter 5 process: requirement → examples → edge cases → pseudocode → data choice → smallest version → tests. (The sequence of skills deliberately mirrors the guide's arc.)

| # | Challenge | Trains |
|---|---|---|
| 1 | Reject duplicate titles (case-insensitive) | invariants; searching state in `Add`; a new validator rule |
| 2 | Add `Priority` (Low/Medium/High) — enum + display | enums as design; migration of the JSON (old files: what default?) |
| 3 | `List` filtered by status (menu 6 → `ListByStatus`) | command dispatch growth; LINQ `Where` on a second axis |
| 4 | `Due today` command (uses `DateTime.Today`) | date logic; UTC vs local (14.6) made real |
| 5 | Edit a task's title/description | the update pattern (17.4) on more fields |
| 6 | Confirm before deletion (`y/n` via `InputReader`) | destructive-action safety; reuse over invention |
| 7 | Export tasks to CSV | a second serialization format; escaping commas/quotes |
| 8 | Import from CSV *with full validation* | parsing hostile text (7.6's five questions); partial-failure policy |
| 9 | Unit tests for **every** manager operation | the 19.3 suite grown systematic; regression discipline (12.8) |
| 10 | Replace JSON with SQLite (new repository class only!) | 21.3's promise — measure how little changes |
| 11 | Add an ASP.NET Core API beside the console UI | 21.2 — one brain, two faces |
| 12 | A web or desktop UI (Blazor/MAUI — your choice) | views over the same service |
| 13 | User accounts and authorization | security principles (21.6) in earnest |
| 14 | Logging + error reporting (replace `Console.WriteLine` in errors) | 21.5's flight recorder, retrofitted |
| 15 | Measure and improve search performance at 100k tasks | 11.6's discipline: measure first; maybe an index; maybe "do nothing, 100ms is fine" — *with evidence* |

The finish line of challenge 15 is not "fast code" — it is *measured code with a defensible decision*. That is mastery's signature.

#### 22.3 Mastery questions — audit yourself honestly

You are making real progress when each of these has an *instant, specific* answer for any code you wrote — no guessing, no hand-waving:

1. What is the input and output of this method? *(9.2's signature)*
2. What assumptions does this code make? *(14.5's "exceptional" line)*
3. What happens for an **empty** collection? A **null**? A **huge** value? *(5.4's list)*
4. What is the time complexity — and at what input size does it start to matter? *(11.3, 11.5)*
5. What is the memory complexity? *(10.4's copies; 6.4's references)*
6. Which class owns this rule — and could a second copy of it exist elsewhere? *(9.9, 13.4)*
7. Can this code be tested without a terminal, file system, or clock? *(13.5, 19.3)*
8. What changes if the data source becomes a database? *(21.3 — "one class" is the passing answer)*
9. What would fail if two users did this at the same time? *(21.1 — Level 4's question)*
10. What did I predict, what actually happened, and what did the gap teach me? *(4.9, the loop under everything)*

#### 22.4 How to keep growing

- **Keep a solved-problems journal.** One page per problem: the five parts, the wrong first idea, the fix, the lesson. Chapter 5's process *recorded* becomes your own textbook, personally fitted.
- **Read other people's code** — start with the .NET runtime's own source (it is open on GitHub; `string.IsNullOrEmpty` is one readable file, and 15.5's `System.Threading.Tasks.TaskStatus` lives there too).
- **Deliberately break your working programs** — corrupt your JSON (16.3 already did), delete a `;` (4.8), swap `==` for `=` (6.12) — every time predicting the error *before* reading it. Prediction practice is immune to tutorial drift.
- **Teach it.** Explaining `FirstOrDefault` to a colleague (or a rubber duck — 4.6) is the final exam of every chapter here.
- **Ship something.** A tool you actually use beats a thousand tutorials — and you already own one: Task Master, challenge by challenge, until it is *yours* in every line.

---

## Appendices

The appendices are your reference shelf: return to them whenever a word, a symbol, an error code, or a step of the process slips your mind. They are deliberately compact — every entry is explained in depth somewhere in the guide, and using an appendix entry should send you back to the chapter that owns the concept.

---

### Appendix A — C# Vocabulary

| Term | Meaning | Deep dive |
|---|---|---|
| Algorithm | A finite sequence of precise steps solving a problem, independent of any language | Ch. 1.4 |
| Argument | An actual value supplied in a method call (fills a parameter) | Ch. 9.2 |
| Array | A fixed-length sequence of values, indexed from zero | Ch. 10.2 |
| Assertion | A statement that a fact must hold at a point in code; trips loudly if violated | Ch. 12.5 |
| Assignment | Giving a variable a value with `=` | Ch. 6.2 |
| Asynchronous | Waiting for slow operations without blocking the program | Ch. 20.8 |
| Big O | Notation describing how cost grows with input size | Ch. 11.3 |
| Boolean / `bool` | A true-or-false value; the fuel of every decision | Ch. 6.3 |
| Class | A named type describing data and behavior; a blueprint | Ch. 13.2 |
| Collection | An object holding many values (array, list, dictionary, set, queue, stack) | Ch. 10 |
| Compiler | The program that translates and type-checks your source before running | Ch. 3.2 |
| Complexity | How an algorithm's resource usage scales with input size | Ch. 11 |
| Composition | Building behavior by combining focused objects ("has-a") | Ch. 13.7 |
| Constructor | Special method that runs during `new`; makes an object start valid | Ch. 13.3 |
| Debugging | Systematic evidence-gathering to find why behavior differs from intent | Ch. 12.3 |
| Dependency | A component another component needs to do its job | Ch. 13.5 |
| Dependency injection | Providing dependencies from outside instead of constructing inside | Ch. 21.4 |
| Deserialization | Parsing stored text (JSON) back into live objects | Ch. 14.4 |
| Edge case | An unusual, extreme, or hostile input that must be handled deliberately | Ch. 5.4 |
| Encapsulation | Hiding data behind the methods that protect it | Ch. 13.4 |
| Enum | A fixed set of named values; type-safe vocabulary | Ch. 15.3 |
| Exception | An object representing an exceptional failure, thrown/catchable | Ch. 14.5 |
| Expression | Code that produces a value (`10 + 5`, `age >= 18`) | Ch. 6.6 |
| Field | A variable stored as part of an object (`_tasks`) | Ch. 13.3 |
| Garbage collection | The runtime automatically reclaiming memory you stopped using | Ch. 3.2 |
| Generic | A type or method parameterized by another type (`List<T>`) | Ch. 10.3 |
| Guard clause | An early check that rejects invalid input before the main logic | Ch. 9.8 |
| Invariant | A condition that must remain true throughout execution | Ch. 20.6 |
| Interface | A contract of members a class promises to provide (`IClock`) | Ch. 13.5 |
| Iteration | One repetition of a loop body | Ch. 8.4 |
| Lambda | A short anonymous function (`n => n > 3`) | Ch. 10.10 |
| LINQ | Library + language methods for querying collections readably | Ch. 10.10 |
| Literal | A value written directly in code (`25`, `"hello"`, `true`) | Ch. 6.2 |
| Memoization | Caching subproblem results so each is solved once | Ch. 20.4 |
| Method | A named block of executable behavior, possibly taking parameters and returning a value | Ch. 9 |
| Namespace | A named group for related types, preventing name collisions | Ch. 15.3 |
| Null | The absence of a value; "nothing is in this reference" | Ch. 6.10 |
| Nullable type | A type that may hold a value or null (`DateTime?`, `string?`) | Ch. 6.10 |
| Object | A live instance of a class, created with `new` | Ch. 13.2 |
| Parameter | A declared input placeholder in a method's definition | Ch. 9.2 |
| Persistence | Data surviving restarts by being stored externally | Ch. 14.1 |
| Polymorphism | One call site invoking different concrete implementations | Ch. 13.6 |
| Program | An algorithm expressed in a language precisely enough to execute | Ch. 1.4 |
| Property | A member exposing data through `get`/`set`, possibly computed | Ch. 13.3 |
| Pseudocode | A solution written in structured plain language before coding | Ch. 1.6 |
| Recursion | A method solving a smaller copy of its own problem | Ch. 20.1 |
| Refactoring | Changing structure with behavior provably preserved (tests green) | Ch. 19.4 |
| Repository | A class solely responsible for save/load of a data type | Ch. 16.1 |
| Runtime (CLR) | The environment that loads, verifies, and executes your program | Ch. 3.1 |
| Scope | The region of code where a name is usable | Ch. 9.5 |
| Serialization | Converting live objects into storable text (JSON) | Ch. 14.4 |
| Short-circuiting | `&&`/`\|\|` stopping evaluation once the answer is certain | Ch. 6.7 |
| Statement | An instruction performing an action, ended by `;` | Ch. 4.6 |
| Syntax | The grammar rules of the language | Ch. 1.5 |
| Semantics | The meaning of grammatically valid code | Ch. 1.5 |
| Test (unit) | An automated AAA check of one behavior, runnable in milliseconds | Ch. 12.6 |
| Type | The definition of what kind of value something is and what it can do | Ch. 6.3 |
| Validation | Checking input against rules before using it | Ch. 7.3 |
| Variable | A named storage location in memory | Ch. 6.2 |

---

### Appendix B — C# Symbols

| Symbol | Common meaning | Deep dive |
|---|---|---|
| `;` | End of a statement | Ch. 4.6 |
| `{ }` | A code block; also object/collection initializers | Ch. 8.2, 14.4 |
| `( )` | Method parameters / arguments; grouping; conditions | Ch. 4.6 |
| `[ ]` | Array indexing; attributes (metadata) | Ch. 10.2, 12.6 |
| `.` | Member access: "look inside this type/object" | Ch. 4.6 |
| `=` | Assignment | Ch. 6.2 |
| `==` | Equality comparison (and `!=` inequality) | Ch. 6.7 |
| `<` `>` `<=` `>=` | Ordering comparisons; also generic parameters (`List<T>`) | Ch. 6.7, 10.3 |
| `&&` `\|\|` `!` | Logical AND, OR, NOT (short-circuiting) | Ch. 6.7 |
| `+` `-` `*` `/` `%` | Arithmetic (modulus = remainder) | Ch. 6.6 |
| `++` `--` `+=` `*=` | Increment, decrement, compound assignment | Ch. 6.6 |
| `=>` | Lambda arrow; expression-bodied member; switch-expression arm | Ch. 9.4, 10.10, 19.1 |
| `?:` | Conditional (ternary): `condition ? ifTrue : ifFalse` | Ch. 17.3 |
| `??` | Null-coalescing: left if not null, else right | Ch. 6.10 |
| `?.` | Null-conditional: access member only if not null | Ch. 6.10 |
| `?` (after type) | Nullable: may hold a value or null (`DateTime?`) | Ch. 6.10 |
| `new` | Construct a new object from a type | Ch. 10.3, 13.2 |
| `throw` | Raise an exception | Ch. 9.8 |
| `nameof` | The *name* of a symbol as compile-checked text | Ch. 9.8 |
| `//` `/* */` `///` | Single-line, multi-line, XML documentation comments | Ch. 4.7 |
| `$"..."` | Interpolated string: `{holes}` evaluated inside | Ch. 6.8 |

---

### Appendix C — Compiler Error Decoder

The errors every beginner meets, decoded. **First, always:** read the whole message — C# errors state *where* (file, line, column), *what*, and usually *why*.

| Code | Typical message | What actually happened | Fix |
|---|---|---|---|
| CS1002 | `; expected` | A statement is incomplete — usually a missing semicolon (reported at the *first* place the grammar broke) | Add the `;` at the reported position; check the line *above* too |
| CS1513 | `} expected` | Unbalanced braces — one `{` was never closed | Indent properly and count braces; editors highlight the match |
| CS0103 | `The name 'titel' does not exist in the current context` | Typo, undeclared variable, or missing `using` | Fix the spelling; declare the variable; add the namespace import |
| CS0246 | `The type or namespace name 'TaskIteam' could not be found` | Type name typo or missing project reference/import | Fix the name; add `using`/project reference |
| CS0029 | `Cannot implicitly convert type 'string' to 'int'` | Assigning across types with no automatic conversion (e.g., `int age = "twenty";`) | Convert deliberately: `TryParse`, or the right literal |
| CS0019 | `Operator '==' cannot be applied to operands of type 'int' and 'string'` | Comparing mismatched types | Convert one side; store types consistently |
| CS0104 | `'TaskStatus' is an ambiguous reference between 'A' and 'B'` | Two imported namespaces contain the same type name (your **15.5** battle scar) | Qualify fully or add a `using X = ...;` alias |
| CS0122 | `'X' is inaccessible due to its protection level` | Using a `private` member from outside its class | Go through the public API (13.4's door), or widen access deliberately |
| CS0165 | `Use of unassigned local variable 'n'` | Reading a local before definitely assigning it | Initialize (`int n = 0;`) or restructure the control flow |
| CS0161 | `': not all code paths return a value` | A non-void method can reach the end without `return` | Add the missing return path (often the final `else`/fallback) |
| CS0201 | `Only assignment, call, ... can be used as a statement` | A bare expression statement with no effect (`a + b;`) | Assign the result somewhere or remove the line |
| CS1061 | `'TaskItem' does not contain a definition for 'Titel'` | Misspelled *member* on an instance/type | Fix the member name; IntelliSense/metadata is your friend |
| CS0117 | `'Math' does not contain a definition for 'Maxx'` | Same, but accessed through the type name | Same |
| CS1503 | `Argument 1: cannot convert from 'int' to 'string'` | Argument type mismatch in a call | Pass the right type; overloads pick by type |
| CS5001 | `Program does not contain a static 'Main' method suitable for an entry point` | `Program.cs` has classes but no `Main` (and no top-level statements) | Add `static void Main()` or a top-level statement |
| CS8803 | `Top-level statements must precede namespace and type declarations` | In a top-level program, statements come *before* any class/namespace in the file | Move type declarations to the end or into separate files |
| CS86xx *warnings* | `CS8602 dereference of a possibly null reference`, `CS8604 possible null argument` | The nullable analyzer flags a path where null could flow | Handle the null (6.10's patterns); these warnings are bugs found *before* runtime |

**Reading any error, the universal four steps:** (1) where — file/line/column; (2) what — the code + one-line summary; (3) compare with your *intention* on that line (the error is usually one line above what you expected); (4) fix the *cause*, not the message (deleting code until silence is not repair).

---

### Appendix D — The Problem-Solving Checklist

Print this. Use it on every problem, from exercises to production features.

**Before coding:**

- [ ] Can I state the problem in one precise sentence?
- [ ] Inputs: what enters, from whom, in what format?
- [ ] Output: what result, exactly, in which cases?
- [ ] Rules: what must always be true?
- [ ] Constraints: what can fail or be missing around me?
- [ ] Success measure: how will I *prove* it works?
- [ ] Have I written 3–5 concrete examples (input → expected)?
- [ ] Have I hunted edge cases: empty / whitespace / zero / one / huge / negative / duplicates / wrong type / missing resource / hostile input?
- [ ] Can I write the pseudocode before any C#?
- [ ] Which data structure fits the operations (order? lookup? uniqueness? growth?)?
- [ ] What is the smallest working version I can build first?

**While coding:**

- [ ] Do names say what things are (no `DoIt`, no `x`)?
- [ ] Does each method have one responsibility?
- [ ] Am I validating every external input before use?
- [ ] Is each rule enforced in exactly one home?
- [ ] Does it compile after each small change (4.8's loop)?
- [ ] Can I explain every line I typed — aloud?

**After coding:**

- [ ] Tested normal cases?
- [ ] Tested empty / boundary (min, max, max+1) values?
- [ ] Tested invalid input — with a message, not a crash?
- [ ] Tested repeated operations (add ten, delete all, delete one more)?
- [ ] Tested persistence / external failures (missing file, corrupted file)?
- [ ] Did I measure performance if data can grow (11.6)?
- [ ] Did every bug found become a regression test (12.8)?
- [ ] Could another person follow the design without me (21.8)?
- [ ] Did I record what I learned (22.4's journal)?

---

### Appendix E — `dotnet` CLI Quick Reference

Every command used in this guide, plus the few you will meet next. Format: what it does — the words that matter.

| Command | What it does | Introduced |
|---|---|---|
| `dotnet --version` | Print the installed SDK version | Ch. 4.1 |
| `dotnet new console -n Name` | Create a console project from the template (`-n` = name) | Ch. 4.4 |
| `dotnet run` | Build (if needed) and run the project | Ch. 4.4 |
| `dotnet build` | Compile only; report errors/warnings without running | Ch. 15.6 |
| `dotnet new xunit -n Name.Tests` | Create a test project (xUnit template) | Ch. 12.6 |
| `dotnet add Name.Tests reference Name` | Make the test project see the app project's public types | Ch. 12.6 |
| `dotnet add package SomePackage` | Install a NuGet library into the project | Ch. 3.1 |
| `dotnet test` | Build + run every `[Fact]`/`[Theory]` test; print pass/fail | Ch. 12.6 |
| `dotnet list package --outdated` | Show installed libraries with newer versions available | Ch. 21.6 |
| `dotnet publish -c Release` | Produce a deployable output (Release configuration) | Ch. 21 |
| `dotnet clean` | Delete build outputs (`bin`/`obj`) — the "turn it off and on" of builds | as needed |
| `dotnet --list-sdks` | List every installed SDK version | Ch. 4 |
| `dotnet new sln` | Create a solution file — the container that holds multiple projects together (app + tests) | Ch. 19 |

A note on `dotnet run` vs `build` vs `publish`: `run` is the inner loop (seconds); `build` is the checkpoint habit; `publish` is the exit door — Release configuration, trimmed and ready for a machine that has no SDK installed.

---

## Final Message to the Learner

Problem solving is not a talent that some people are born with and others are denied. It is a *trainable process* — and you have now trained it, chapter by chapter, from the definition of a problem to a tested, layered, persistent application:

> **Understand the problem → model the data → write precise steps → build the smallest version → test normal, edge, and hostile cases → debug from evidence → refactor safely → grow the design outward.**

C# was the tool you used to express those steps — and a fine tool it is: strict enough to teach you precision, rich enough to carry you from a terminal to the web, the cloud, and games. But the syntax was never the point, and this guide never pretended otherwise. The point was learning to think clearly enough that every line of syntax has a precise job.

Start with the first exercise you have not done. Run every example. Make deliberate mistakes and read every message the compiler sends you — it is the most patient teacher you will ever have. Keep a record of the problems you solve, and teach what you learn, because teaching is the final exam.

That is how you go from zero knowledge to mastery. Not in one leap — in one small, understood, tested step at a time. You already know the way; you have walked it.

*Now go build something.*

