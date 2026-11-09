
# Access Modifiers in TypeScript OOP

## Introduction

Access modifiers in TypeScript support the **Encapsulation** pillar of Object-Oriented Programming (OOP) by controlling access to class properties and methods. TypeScript provides `public`, `private`, and `protected` to manage visibility, while `readonly` prevents reassignment after initialization, helping protect data and maintain controlled access to class members.

## Detailed Explanation

- **Public:** A `public` member is accessible from anywhere, both inside and outside the class. It is the default access modifier when none is specified.

- **Private:** A `private` member can only be accessed within the class where it is declared.

- **Protected:** A `protected` member is accessible within its declaring class and its subclasses, but not through an external instance.

- **Readonly:** A `readonly` property can be initialized during declaration or inside the constructor, but its value cannot be reassigned afterward.

```ts
class Employee {
  public name: string;
  private salary: number;
  protected department: string;
  readonly employeeId: number;

  constructor(
    name: string,
    salary: number,
    department: string,
    id: number
  ) {
    this.name = name;
    this.salary = salary;
    this.department = department;
    this.employeeId = id;
  }

  public getSalary(): number {
    return this.salary;
  }
}

class Manager extends Employee {
  getDepartment(): string {
    return this.department; // Allowed: protected member
  }
}
```

- `Employee` defines a class with four properties: `name` (`public`), `salary` (`private`), `department` (`protected`), and `employeeId` (`readonly`).
- The constructor initializes all four properties when an `Employee` object is created.
- `getSalary()` is a public method that allows access to the private `salary` property from outside the class.
- `Manager` extends the `Employee` class, inheriting its accessible properties and methods.
- `getDepartment()` accesses the protected `department` property, which is allowed because `Manager` is a subclass of `Employee`.
- The `employeeId` property can be accessed but cannot be reassigned after initialization.


## Conclusion

Access modifiers are essential for implementing encapsulation in TypeScript OOP. They control the visibility of class members, protect sensitive data, and define how properties and methods can be accessed. Using the appropriate modifiers makes code more secure, organized, and maintainable.
