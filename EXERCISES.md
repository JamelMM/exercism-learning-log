# Exercism C# Exercise Index

This file tracks my completed Exercism C# exercises and the main concept practiced in each one.

## Completed Exercises

| # | Exercise | Main Concept | Reusable Pattern |
|---|---|---|---|
| 1 | Hello World | Basic method and return value | Return a fixed value from a method |
| 2 | Lucian's Luscious Lasagna | Methods, parameters, and arithmetic | Use small methods to calculate simple values |
| 3 | Annalyn's Infiltration | Booleans and logical operators | Combine conditions with `&&`, `||`, and `!` |
| 4 | Bird Watcher | Arrays and indexes | Read, update, and aggregate array values |
| 5 | Secure Manchester United | Interfaces, inheritance, and type checks | Check specific types before general parent types |
| 6 | Squeaky Clean | Strings, chars, and text transformation | Iterate over text and build a cleaned result |
| 7 | Jedlik's Toys | Classes, object state, and instance methods | Store state in fields and update it through methods |
| 8 | Authentication System | Constants, defensive copying, and readonly collections | Protect internal data by returning readonly wrappers |
| 9 | Need for Speed | Object state, encapsulation, and loops | Simulate repeated actions until a goal is reached |
| 10 | Booking Up for Beauty | DateTime parsing and time comparisons | Use DateTime properties and comparisons to model time-based rules |
| 11 | International Calling Connoisseur | Dictionaries and key-value pairs | Store values by key and safely read, update, remove, and iterate entries |
| 12 | Logs, Logs, Logs | Enums, string parsing, and switch statements | Extract a code from text and map it to a typed enum value |
| 13 | Face ID 2.0 | Equality, hash codes, and reference comparison | Override Equals/GetHashCode for value equality and use ReferenceEquals for object identity |
| 14 | Simple Calculator | Exceptions and input validation | Validate inputs first, then execute the requested operation |
| 15 | The Weather in Deather | Expression-bodied members, ternary conditionals, switch expressions, and throw expressions | Map object state to enum results using compact rule-based expressions |

## Learning Patterns

### Text transformation

Practiced in:
- Squeaky Clean

Pattern:
Read each character, decide what to do with it, and append the result to a new string.

### Object state

Practiced in:
- Jedlik's Toys

Pattern:
Keep data inside the object and let instance methods read or update that state.

### Type checks and inheritance

Practiced in:
- Secure Manchester United

Pattern:
When using inheritance, check specific child types before general parent types.

### Array processing

Practiced in:
- Bird Watcher

Pattern:
Use indexes and loops to read, update, count, or summarize array values.

### Boolean logic

Practiced in:
- Annalyn's Infiltration

Pattern:
Translate rules into boolean expressions using `&&`, `||`, and `!`.

### Protecting internal collections

Practiced in:
- Authentication System

Pattern:
Keep mutable data private, and expose a readonly wrapper when external code should only be able to read it.

Key idea:
`readonly` prevents a field from being reassigned, but it does not make the contents of a mutable collection immutable.

Example:
A `Dictionary` can be stored internally, but returned as a `ReadOnlyDictionary` to prevent outside code from changing its entries.

### Constants for fixed values

Practiced in:
- Authentication System

Pattern:
Use `const` for values that are fixed and known at compile time.

### Simulating repeated actions

Practiced in:
- Need for Speed

Pattern:
While an object can still continue, perform one action, then check whether the goal has been reached.

Example idea:
A car repeatedly drives while its battery is not drained. After each drive, check whether it has reached the track distance.

Example:
Fixed values like allowed eye colors can be represented as constants.
### Date and time rules

Practiced in:
- Booking Up for Beauty

Pattern:
Use `DateTime.Parse`, `DateTime.Now`, and properties like `.Hour` or `.Year` to model rules based on dates and times.

Common mistake:
`new DateTime()` does not mean "now"; it creates the default date value.

### Dictionary lookup and updates

Practiced in:
- International Calling Connoisseur

Pattern:
Use a dictionary when values should be accessed through unique keys.

Key operations:
- `Add(key, value)` to insert a new entry
- `ContainsKey(key)` to check whether a key exists
- `dictionary[key]` to read or update an existing value
- `Remove(key)` to delete an entry
- `foreach` with `KeyValuePair<TKey, TValue>` to iterate over entries

Common mistake:
A dictionary is not indexed by position. `dictionary[i]` searches for the key `i`.

### Parsing text into enum values

Practiced in:
- Logs, Logs, Logs

Pattern:
Extract the relevant part of a string, then use a `switch` to convert it into a strongly typed enum value.

Key ideas:
- `enum` represents a fixed set of possible values
- `IndexOf` finds character positions
- `Substring` extracts part of a string
- `switch` maps text codes to enum members

Substring formula:
```csharp
text.Substring(start + 1, end - start - 1)
```
**Use it when extracting text between two delimiters.**

Common mistake:
An enum does not store string values. The parsing logic belongs in a method.

### Value equality vs reference equality

Practiced in:
- Face ID 2.0

Pattern:
Use `Equals` to define logical equality for a class, and use `ReferenceEquals` when you need to know whether two variables point to the exact same object.

Key ideas:
- classes compare by reference by default
- `Equals` can be overridden to compare values
- `GetHashCode` should be overridden when `Equals` is overridden
- fields used in `Equals` should also be used in `GetHashCode`
- `ReferenceEquals(a, b)` checks object identity, not value equality

Common mistake:
Overriding `Equals` without also overriding `GetHashCode`, which can cause incorrect behavior in `Dictionary` or `HashSet`.

### Input validation with exceptions

Practiced in:
- Simple Calculator

Pattern:
Validate inputs at the beginning of a method and throw an appropriate exception when the method cannot continue.

Key ideas:
- `ArgumentNullException` for `null`
- `ArgumentException` for an invalid general argument
- `ArgumentOutOfRangeException` for unsupported values
- guard conditions keep the main logic easier to follow

### Compact rule-based logic

Practiced in:
- The Weather in Deather

Pattern:
When object state maps to a specific result, use expression-bodied members, ternary conditionals, switch expressions, or throw expressions to keep the rule close to the value it returns.

Key ideas:
- use expression-bodied members for simple methods and properties
- use ternary conditionals for small two-way decisions
- use switch expressions for multiple related outcomes
- use tuple patterns when a decision depends on more than one value
- use `_` as a wildcard pattern for values that do not matter

## Notes

The goal of this repository is not only to store solutions, but to track my progress in C#, problem solving, and algorithmic thinking.
