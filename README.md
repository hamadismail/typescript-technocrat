# What is the Use of Enums in TypeScript?

_By Hamad Ismail_

---

TypeScript, a superset of JavaScript, offers several powerful features that enhance developer experience—one of them being **Enums**. Enums (short for _enumerations_) allow developers to define a set of named constants, improving code readability and reducing errors from magic numbers or strings.

## Why Use Enums?

Enums help:

- Organize and group related values
- Make code more descriptive and self-documenting
- Prevent invalid values through type-checking
- Enable easy iteration when needed

Let’s explore two types of enums in TypeScript: **numeric** and **string**.

---

## Numeric Enum Example

In a numeric enum, TypeScript automatically assigns incremental numeric values starting from 0, unless specified otherwise.

```ts
enum Direction {
  North, // 0
  East, // 1
  South, // 2
  West, // 3
}

let travel = Direction.North;
console.log(travel); // Output: 0
console.log(Direction[0]); // Output: 'North'
```

You can also manually set the starting value:

```ts
enum Direction {
  North = 1,
  East,
  South,
  West,
}

console.log(Direction.South); // Output: 3
```

---

## String Enum Example

In a string enum, each member is explicitly assigned a string value.

```ts
enum Status {
  Success = 'SUCCESS',
  Failure = 'FAILURE',
  Pending = 'PENDING',
}

let response: Status = Status.Success;
console.log(response); // Output: 'SUCCESS'
console.log(Status.Failure); // Output: 'FAILURE'
```

Unlike numeric enums, **reverse mapping** is not supported for string enums:

```ts
console.log(Status['SUCCESS']); // Output: undefined
```

---

## Conclusion

Enums in TypeScript are a powerful tool to make your code cleaner, more readable, and less error-prone. Whether you're grouping status codes, directions, or types of actions, enums provide a robust way to define and manage sets of related values.

---

_Thanks for reading! Follow for more TypeScript tips and tricks._
