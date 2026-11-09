
# Type Aliases vs. Interfaces in TypeScript

## Introduction

TypeScript offers both `type` aliases and `interface` declarations for describing the shape of data. They often look interchangeable, especially when defining object properties. However, they support different capabilities, so choosing deliberately makes code easier to maintain.

## Detailed Explanation

### Interface

An `interface` is a TypeScript feature used to define the structure or blueprint of an object. It specifies which properties and methods an object must have, along with their respective types. 

```ts
interface Student {
  id: number;
  name: string;
  enrolledCourses: string[];
}

const student1: Student = {
  id: 101,
  name: "Shafin",
  enrolledCourses: ["TypeScript", "React", "Node.js"]
};
```

- `Student` defines an object structure with three properties: `id`, `name`, and `enrolledCourses`.
- `student1` creates a variable using the `Student` interface, storing the student's ID, name, and enrolled courses.

### Types

A `type` alias in TypeScript allows developers to create a custom name for an existing type or a combination of types. It can represent primitive values, objects, arrays, union types, intersection types, and more.

```ts
type Address = {
    present: string;
    permanent: string;
};

type Role = "TEACHER" | "STUDENT";

const userAddress: Address = {
    present: "Chittagong",
    permanent: "Dhaka"
};

const userRole: Role = "STUDENT";

```

- `Address` defines an object structure with two properties: `present` and `permanent`, both of type `string`.
- `Role` defines a union type that only accepts two possible values: `"TEACHER"` or `"STUDENT"`.
- `userAddress` creates a variable following the `Address` type structure, storing the user's present and permanent addresses.
- `userRole` creates a variable using the `Role` type, allowing only the predefined values.


### Key Differences Between Interface and Type Alias

An `interface` is mainly used to define object structures and supports inheritance (`extends`) and declaration merging. A `type` alias is more flexible, supporting objects, primitives, unions (`|`), intersections (`&`), and tuples, but does not support declaration merging.

## Conclusion

`interface` is used when defining object structures that require inheritance or declaration merging. `type` is used when working with unions, intersections, primitives, tuples, or complex type combinations.