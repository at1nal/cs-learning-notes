# CS50 Week 0 — Scratch

> Notes from CS50 Week 0 on computational thinking, data representation, algorithms, abstraction, and Scratch.

---

## Table of Contents

- [1. Computer Science and Problem Solving](#1-computer-science-and-problem-solving)
- [2. AI and Programming](#2-ai-and-programming)
- [3. Data Representation](#3-data-representation)
- [4. Binary](#4-binary)
- [5. ASCII and Unicode](#5-ascii-and-unicode)
- [6. Images, Video, and Audio](#6-images-video-and-audio)
- [7. Algorithms](#7-algorithms)
- [8. Pseudocode](#8-pseudocode)
- [9. Core Programming Concepts](#9-core-programming-concepts)
- [10. Abstraction](#10-abstraction)
- [11. Scratch](#11-scratch)
- [12. Key Takeaways](#12-key-takeaways)

---

## 1. Computer Science and Problem Solving

Computer science is basically about **problem solving**.

A problem can be represented as:

```text
Input
  ↓
Algorithm
  ↓
Output
```

- **Input** — information given to the program
- **Algorithm** — step-by-step instructions used to solve the problem
- **Output** — the result


### Computational Thinking

**Computational thinking** means applying ideas from computer science to problems.

This includes thinking about:

- how information can be represented
- how a problem can be broken into smaller parts
- how an algorithm can solve the problem
- whether the solution is correct and efficient

The main point of CS50 is not just learning how to write code.

Programming languages are tools. The bigger goal is learning how to approach problems clearly and eventually being able to pick up new languages and technologies on your own.

---

## 2. AI and Programming

AI can help programmers with things like:

- finding bugs
- explaining code
- generating implementations
- adding features

But understanding the fundamentals is still important.

A programmer still needs to know:

- what problem is being solved
- what behaviour is expected
- whether the output is actually correct
- why something works
- how to identify and fix mistakes

So AI can help with implementation, but it does not replace understanding what the program is doing.


### APIs

An **API (Application Programming Interface)** gives software a way to interact with another system or service.

Roughly:

```text
Program
   ↓
  API
   ↓
External service
   ↓
Response
```

For example, instead of building an AI model from scratch, a program can send a request to an existing AI service through its API.

The important part is that we can use the service without needing to know how everything inside it works.


### `import` vs API

These are related, but they are not the same thing.

An `import` makes code from another module or library available inside a program.

For example:

```python
from openai import OpenAI
```

This makes `OpenAI` from the `openai` package available to the Python program.

An **API** is the interface used for communication between software systems.

A simple way to separate them:

```text
import
→ gives the program access to code / tools

API
→ lets software communicate with another system or service
```

For the lecture example:

```text
Python program
      ↓
OpenAI library
      ↓
OpenAI API
      ↓
OpenAI service / model
      ↓
response
```

So basically:

> **`import` gives the program access to tools, while an API is how software interacts with another system.**


### Prompts

The lecture also introduces two types of prompts:

- **User prompt** — what the user asks
```text
What is CS50?
```
- **System prompt** — instructions that control how the AI should behave
```text
Limit your answer to one sentence.
```


### Rubber Duck Debugging

**Rubber duck debugging** means explaining a programming problem step by step, even if the listener is just an inanimate object.

The point is that explaining the logic clearly often makes the mistake easier to spot.

---

## 3. Data Representation

Computers ultimately represent information using:

```text
0
1
```

These two values can represent different kinds of information depending on context:

- numbers
- characters
- colors
- images
- audio
- video
- instructions

The key idea is:

> The bits themselves do not tell us what they mean. The context tells the computer how to interpret them.

The same pattern of bits could represent a number in one situation and a character or color in another.

---

## 4. Binary

A **bit** is a single binary digit.

```text
bit = 0 or 1
```

Binary works well for computers because electronic components can represent two states.

A simple way to picture it is:

```text
0 = off
1 = on
```

Computers use huge numbers of tiny electronic switches called **transistors** to represent these states.
> same idea as using 5 fingers to count from 0~31, giving 2⁵ = 32 possible combinations.


### Number Systems

The **base** tells us how many digits are available in a number system.

| System | Base | Digits |
| --- | ---: | --- |
| Unary | 1 | one symbol |
| Binary | 2 | `0`, `1` |
| Decimal | 10 | `0`–`9` |

Binary matters most for computers because two states map naturally to electronic on/off states.


### Decimal

Decimal is **base 10**.

It uses ten digits:

```text
0 1 2 3 4 5 6 7 8 9
```

For example:

```text
123
= 1 × 10²
+ 2 × 10¹
+ 3 × 10⁰
```

The place values are powers of 10:

```text
100  10  1
```


### Binary

Binary is **base 2**.

It only uses:

```text
0 1
```

Its place values are powers of 2:

```text
128 64 32 16 8 4 2 1
```

For example:

```text
111₂
= 4 + 2 + 1
= 7₁₀
```


### Binary Counting

| Decimal | Binary |
| ---: | :--- |
| 0 | `000` |
| 1 | `001` |
| 2 | `010` |
| 3 | `011` |
| 4 | `100` |
| 5 | `101` |
| 6 | `110` |
| 7 | `111` |

To represent `8`, another bit is needed:

```text
1000
```


### Bytes

One **byte** contains eight bits.

```text
1 byte = 8 bits
```

Eight bits give:

```text
11111111 = 2⁸ = 256
```

possible combinations.

If the values start from `0`, one unsigned byte can represent:

```text
0 to 255
```

This is why `255` and `256` show up so often in computing.

---

## 5. ASCII and Unicode

Computers can represent text by assigning numbers to characters.


### ASCII

**ASCII (American Standard Code for Information Interchange)** maps characters to numbers.

For example:

```text
A = 01000001 = 65
B = 01000010 = 66
C = 01000011 = 67
```

So if the computer sees the binary representation of `65` in a text context, it can interpret it as:

```text
A
```


### Uppercase and Lowercase

In ASCII:

```text
A = 01000001 = 65
a = 01100001 = 97
```

The difference is:

```text
97 - 65 = 32
```

Changing uppercase to lowercase is a nice example of how something that looks high-level can come down to a simple bit change at a lower level. In ASCII, only one bit needs to change from `0` to `1`, which adds `32` to the value.


### Unicode

ASCII(256) is not enough to represent all languages and symbols.

**Unicode** supports a much larger set of characters, including:

- non-English writing systems
- accented characters
- symbols
- emoji

Emoji are also represented using standardized numerical values.

The same Unicode emoji can look different on Apple, Google, Microsoft, or other platforms, but it still represents the same underlying character.

---

## 6. Images, Video, and Audio

Computers represent media using numbers too.


### RGB

A common way to represent colors is **RGB**:

- **R** — Red
- **G** — Green
- **B** — Blue

Each channel commonly uses a value from:

```text
0 to 255
```

For example:

```text
RGB(0, 0, 0)       → black
RGB(255, 255, 255) → white
```

If each channel uses eight bits:

```text
8 bits × 3 channels
= 24 bits
= 3 bytes
```


### Images

A digital image is made up of **pixels**.

Each pixel has a color, which can be represented using values such as RGB.

```text
Image
  ↓
Pixels
  ↓
RGB values
  ↓
Numbers
  ↓
Bits
```


### Video and Audio

A video is basically a sequence of images shown very quickly.

For example:

```text
30 frames per second
≈ 30 images per second
```

Audio can also be represented using numbers for things like:

- frequency / pitch
- duration
- amplitude / volume

So text, images, video, and audio all eventually come back to numerical values stored as bits.

---

## 7. Algorithms

An **algorithm** is a step-by-step process for solving a problem.

The lecture uses searching through a sorted phone book as the main example.

Assume the phone book contains `n` pages.


### Approach 1 — One Page at a Time

Start at the beginning and check every page:

```text
page 1
page 2
page 3
...
```

In the worst case:

```text
n steps
```

The amount of work grows **linearly** with the size of the problem.


### Approach 2 — Two Pages at a Time

Checking two pages at a time reduces the number of steps to roughly:

```text
n / 2
```

But this could skip over the target, so another check is needed to handle that case.

It is faster, but it still grows linearly.


### Approach 3 — Divide the Problem in Half

Because the phone book is sorted:

1. Open to the middle.
2. Check whether the target comes before or after the current page.
3. Throw away the half that cannot contain the target.
4. Repeat.

For example:

```text
1000
 ↓
500
 ↓
250
 ↓
125
 ↓
...
 ↓
 1
```

The number of steps grows approximately as:

```text
log₂(n)
```

This is much better for large inputs.


### Why Efficiency Matters

Suppose the phone book grows from:

```text
1000 pages
```

to:

```text
2000 pages
```

A linear algorithm may require roughly twice as much work.

If the algorithm keeps cutting the problem in half, it only needs about one extra division.


### Correctness vs Efficiency

Just because an algorithm works does not automatically mean it is a good algorithm.

We also care about things like:

- time
- CPU
- memory
- money
- people

So a solution can be:

```text
correct
but inefficient
```

Computer science is interested in both **correctness** and **design**.

---

## 8. Pseudocode

**Pseudocode** describes an algorithm in a human-readable way without worrying about the exact syntax of a programming language.

For example:

```text
'Pick up' phone book
'Open to' middle
'Look at' page

1  [If] (person is on page)
2      'Call' person
3  [Else if[ (person is earlier in book)
4      'Open to' middle of left half of book
5      {Go back to} line 3
6  [Else if] (person is later in book)
7      'Open to' middle of right half of book
8      {Go back to} line 3
9  [Else] ←exceptions
10     'Quit'

'': functions - verbs or actions
[]: conditions
(): boolean expressions - yes / no
{}: loop - cyclical behavior
```

The point is to work out the:

```text
logic
```

before worrying about:

```text
programming-language syntax
```

This makes it easier to focus on whether the solution actually makes sense.


### Edge Cases

Programs also need to handle cases outside the normal expected situation.

For example:

```text
What if the person is not in the phone book?
```

If this case is ignored, the program could behave incorrectly or keep running when it should stop.

So when designing an algorithm, it is important to think about what could go wrong too.

---

## 9. Core Programming Concepts

These concepts show up again and again across different programming languages.


### Functions

A **function** performs an action or solves a smaller problem.

Functions are basically verbs.

Examples:

```text
print
move
say
play
```


### Arguments

**Arguments** are inputs passed into a function.

```text
function(argument)
```

A function can take one or more arguments.


### Return Values

Some functions give a result back.

```text
input
  ↓
function
  ↓
return value
```

That return value can then be used somewhere else, including as the input to another function.


### Variables

A **variable** stores a value under a name.

For example:

```text
score = 0
```

Later:

```text
score = score + 1
```

Good variable names should make it obvious what the value represents.

For example:

```text
score
```

is much clearer than:

```text
x
```

if the value is actually a score.


### Boolean Expressions

A **Boolean expression** is basically a yes/no question.

Its result is:

```text
true
```

or:

```text
false
```

Examples:

```text
x > 5
sprite is touching mouse
person is on page
```


### Conditionals

**Conditionals** let the program choose what to do depending on a condition.

```text
if condition
    ...
else
    ...
```

They are basically a fork in the road.

### Loops

**Loops** repeat instructions.

Examples:

```text
repeat
forever
```

Instead of writing the same instructions again and again, a loop tells the computer to repeat them for us.

---

## 10. Abstraction

**Abstraction** means hiding details that we do not need to think about right now.

For example:

```text
print("hello")
```

can be used without thinking about:

- the exact CPU instructions
- individual transistor states
- how every pixel gets displayed

Those details have already been handled at a lower level.

So instead of rebuilding everything from scratch, programmers can use existing building blocks and focus on the problem they actually want to solve.

Roughly:

```text
Higher-level tools
       ↑
Programming languages
       ↑
Machine instructions
       ↑
Bits / hardware
```

The higher the level, the less we usually need to think about the implementation details underneath.

---

## 11. Scratch

**Scratch** is a graphical programming language.

Instead of typing code syntax, programs are built with drag-and-drop blocks.

The important part is not really Scratch itself. It is the programming concepts Scratch makes easier to see before moving on to languages like C and Python.

These include:

- functions
- arguments
- return values
- variables
- Boolean expressions
- conditionals
- loops
- events
- abstraction


### Scratch Basics

A Scratch project mainly contains:

- **blocks** — programming instructions
- **sprites** — programmable objects
- **stage** — where the program runs

The stage uses an x-y coordinate system.

```text
         +y
         ↑
         |
-x  ←  (0,0)  →  +x
         |
         ↓
         -y
```

Changing `x` moves a sprite left or right.

Changing `y` moves it up or down.


### Input and Return Values

Scratch can ask the user for input:

```text
[ask ("What's your name?")]
```

The result is stored in:

```text
[answer]
```

That value can then be used somewhere else:

```text
[answer] << input 
   ↓
[join ("Hello, " + answer)]
   ↓
[say (join "Hello, " + answer)]
```

So the result from one operation can become the input to another.


### Forever Loops

Interactive programs usually need to constantly check whether something has happened.

For example:

```text
[forever]
    [if (touching (mouse-pointer)) then]
        ...
```

Without `forever`, the condition might only be checked once before the user even has time to interact.


### Parallel Scripts

A sprite can have more than one script running at the same time.

For example:

```text
Script A:
    continuously move downward

Script B:
    continuously check for collision
```

So different behaviours can happen at the same time.


### Custom Functions and Code Reuse

If the same logic appears multiple times, it is usually better to put it into a reusable function.

Instead of repeating:

```text
set x to random position
set y to 180
```

a custom block can be created:

```text
go to top
```

Then the program only needs:

```text
go to top
```

whenever that behaviour is needed.

This avoids duplicated code and makes the program easier to read and change later.

It is also another example of **abstraction**.


### Incremental Development

The Oscar example shows a useful way to build bigger programs.

Instead of trying to make the whole game at once:

```text
Stage and sprites
      ↓
Basic interaction
      ↓
   Movement
      ↓
Reusable functions
      ↓
Score and extra behaviour
```

The general idea is:

```text
Large problem
    ↓
Break into smaller problems
    ↓
Solve each part
    ↓
Combine everything
```

Basically, get one small thing working first, then build on top of it.

---

## 12. Key Takeaways

### [1] Computers ultimately represent information using bits

```text
0 and 1
```

Everything else is built on top of these binary states.


### [2] Context determines what bits represent

The same bits can represent:

```text
numbers
text
colors
images
audio
instructions
```

depending on how the program interprets them.


### [3] Computer science is fundamentally about problem solving

```text
Input → Algorithm → Output
```


### [4] Algorithms should be correct and efficient

A program working correctly does not necessarily mean it is well designed.


### [5] The same programming concepts appear across languages

Important ones from Week 0:

- functions
- arguments
- return values
- variables
- Boolean expressions
- conditionals
- loops


### [6] Abstraction lets us ignore unnecessary details

We can use existing tools and building blocks without understanding every implementation detail underneath.


### [7] Bigger programs are easier to build in smaller pieces

```text
Big problem
    ↓
Smaller problems
    ↓
Solve individually
    ↓
Combine
```


### [8] Languages change, but the underlying ideas stay similar

Scratch, C, Python, and other languages may look different, but many of the core concepts transfer between them.

---

## Quick Reference

| Term | Meaning |
| --- | --- |
| **bit** | One binary digit: `0` or `1` |
| **byte** | 8 bits |
| **binary** | Base 2 number system |
| **decimal** | Base 10 number system |
| **ASCII** | Early character encoding standard |
| **Unicode** | Character standard supporting a much larger set of languages and symbols |
| **RGB** | Red, Green, Blue color representation |
| **algorithm** | Step-by-step process for solving a problem |
| **pseudocode** | Human-readable description of an algorithm |
| **Boolean** | A value that is either `true` or `false` |
| **function** | An action or reusable operation |
| **argument** | Input passed into a function |
| **return value** | Output produced by a function |
| **variable** | A named place used to store a value |
| **conditional** | Logic that chooses between different paths |
| **loop** | Repeated execution of instructions |
| **abstraction** | Hiding implementation details that are not currently important |
| **API** | An interface that lets software interact with another system |
| **sprite** | A programmable object in Scratch |
