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

---

# Understanding Union and Intersection Types in TypeScript

_By Hamad Ismail_

---

TypeScript offers powerful type features that help developers write safer and more expressive code. Two such features are **union types** and **intersection types**. They allow you to combine types in flexible ways that match real-world use cases.

In this blog post, we’ll explore what union and intersection types are, when to use them, and provide simple code examples to illustrate their usefulness.

---

## What Are Union Types?

A **union type** allows a variable to hold more than one type of value. It's defined using the pipe (`|`) symbol.

```ts
function printId(id: number | string) {
  console.log('Your ID is: ' + id);
}

printId(101); // Output: Your ID is: 101
printId('abc123'); // Output: Your ID is: abc123
```

In the above example, the `id` parameter can be either a number or a string. This is especially useful when working with APIs or user inputs that may accept multiple formats.

Union types help your functions remain flexible, while still enabling TypeScript to perform type-checking and autocompletion.

---

## What Are Intersection Types?

An **intersection type** combines multiple types into one. The resulting type will have all the properties of the constituent types. It’s declared using the ampersand (`&`) symbol.

```ts
type Person = {
  name: string;
};

type Employee = {
  employeeId: number;
};

type Staff = Person & Employee;

const staffMember: Staff = {
  name: 'Alice',
  employeeId: 4567,
};

console.log(`${staffMember.name} has ID ${staffMember.employeeId}`);
// Output: Alice has ID 4567
```

Here, the `Staff` type must satisfy both `Person` and `Employee`. This is great for building complex object models where a value needs to adhere to multiple structures.

---

## When to Use Each

- Use **union types** when a value can be one of several types:

  - For example: `string | number | boolean`

- Use **intersection types** when a value must satisfy multiple type requirements:
  - For example: combining multiple interfaces for reusable, extendable object types.

---

## Final Thoughts

Union and intersection types in TypeScript offer precise control over the types of values your code can work with. Understanding when and how to use them can significantly improve the quality and flexibility of your TypeScript applications.

---

_Thanks for reading! If you found this helpful, stay tuned for more TypeScript insights._
