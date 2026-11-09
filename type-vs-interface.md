# Type vs. Interface in TypeScript: What's the Difference and When to Use Each?

### Introduction

TypeScript provides two ways to define the shape of data: `type` aliases and `interface`. At first, they may look almost identical, but they have some important differences. Understanding these differences helps developers write cleaner and more maintainable code.

### Understanding the Differences

An `interface` is mainly used to describe the structure of an object. It defines which properties and methods an object should have.

```ts
interface User {
  name: string;
  age: number;
}
```

A `type` alias can also describe an object, but it is more flexible. It can define primitive types, unions, intersections, tuples, and more.

```ts
type User = {
  name: string;
  age: number;
};

type Status = "active" | "inactive";
```

One major difference is that interfaces support declaration merging. If two interfaces have the same name, TypeScript combines their properties.

```ts
interface User {
  name: string;
}

interface User {
  email: string;
}
```

Now, the `User` interface contains both properties. Type aliases do not support this feature.

Both can extend other types, but their syntax is slightly different. Interfaces use `extends`, while type aliases commonly use intersection (`&`).

### Conclusion

I generally prefer `interface` when defining object structures, especially in application models and public APIs. For unions, tuples, and more complex type combinations, `type` is usually a better choice. Both are useful, and the right choice depends on what you are trying to achieve.
