Understanding TypeScript's types is essential for writing safer and more predictable code.

This section covers common types you'll encounter in JavaScript and their corresponding representations in TypeScript.

These types form the building blocks for more advanced features and patterns.

# Primitives: `string`, `number`, and `boolean`

Primitives are the basic data types in TypeScript. They include `string` for text, `number` for numeric values, and `boolean` for true/false logic.

These types are foundational for most TypeScript programs and closely mirror their JavaScript counterparts.

```typescript
let message: string = "Hello, TypeScript!";
let age: number = 25;
let isDeveloper: boolean = true;
```

Use lowercase type names (`string`, `number`, `boolean`) instead of the capitalized ones (`String`, `Number`, `Boolean`) as they are more commonly used and recommended.

# Arrays

Arrays are collections of values. In TypeScript, arrays can be defined using two syntaxes:

1. `type[]`
2. `Array<type>`

Both are interchangeable and allow you to define arrays of specific types.

```typescript
let numbers: number[] = [1, 2, 3];
let fruits: Array<string> = ["Apple", "Banana", "Cherry"];
```

This ensures all elements in the array conform to the specified type.

# Tuples

Tuples are a special kind of `array with a fixed number of elements`, where each element can have a different type. 

They are useful for representing structured data with known lengths and types.

```typescript
let person: [string, number] = ["Alice", 30];
```

The tuple above ensures that the first element is always a `string` and the second is a `number`.

# The `any` Type

The `any` type can hold any kind of value, whether it's a `number`, `string`, `object`, etc. 

This gives you a lot of flexibility because you can assign any value to a variable of type `any`. However, using `any` type can be risky because it turns off TS type-checking features, which are designed to catch errors and ensure your code is safe and reliable. 

So, it's best to use `any` only when absolutely necessary.


```typescript
let value: any = 42;
value = "Now a string";
value = { key: "value" };
```

# Type Annotations

Type annotations explicitly declare the type of a variable, function parameter, or return value. They add clarity and help catch errors during development.

```typescript
let name: string = "Alice";
let age: number = 25;
function greet(person: string): string {
  return `Hello, ${person}`;
}
```

In many cases, TypeScript can `infer` the type based on the value, so explicit annotations may not always be necessary.


# Functions

Functions are central to JavaScript and TypeScript development. TypeScript enhances functions with type annotations for `parameters` and `return values`, making them more predictable and reliable.

## Parameter Type Annotations

Type annotations for parameters define the expected input types:

```typescript
function greet(name: string) {
  console.log(`Hello, ${name}`);
}
```

## Return Type Annotations

You can specify the type of value a function returns:

```typescript
function add(x: number, y: number): number {
  return x + y;
}
```

## Functions Returning Promises

When a function returns a `Promise`, you can use the `Promise` type:

```typescript
async function fetchData(): Promise<string> {
  return "Data fetched!";
}
```

Anonymous functions automatically infer parameter types based on the context in which they’re used:

```typescript
const numbers = [1, 2, 3];
numbers.forEach((num) => console.log(num));
```

# Object Types

Object types define the structure of objects by specifying their properties and types. This is one of the most common types you’ll encounter in TypeScript.

```typescript
function printPoint(point: { x: number; y: number }) {
  console.log(`X: ${point.x}, Y: ${point.y}`);
}

printPoint({ x: 5, y: 10 });
```


# Optional Properties

Optional properties allow certain object fields to be optional. Use the `?` modifier to make a property optional.

```typescript
function printName(name: { first: string; last?: string }) {
  console.log(name.first);
  if (name.last) {
    console.log(name.last);
  }
}

printName({ first: "Alice" });
printName({ first: "Alice", last: "Smith" });
```

# Union Types

Union types allow a value to have `one of several types`. This is particularly useful for functions that can handle multiple types of input.

```typescript
function printId(id: number | string) {
  console.log(`ID: ${id}`);
}

printId(101);
printId("ABC123");
```

TypeScript ensures that operations on union types are valid for all possible member types. 

Narrowing with `type guards` can help handle specific cases:

```typescript
function printId(id: number | string) {
  if (typeof id === "string") {
    console.log(id.toUpperCase());
  } else {
    console.log(id.toFixed(2));
  }
}
```

# Literal Types

Literal types represent specific values rather than general types like `string` or `number`. 

They are useful for restricting input to predefined options.

```typescript
function printAlignment(alignment: "left" | "right" | "center") {
  console.log(`Alignment: ${alignment}`);
}

printAlignment("left");
printAlignment("right");
```

You can also use `numeric` and `boolean` literal types:

```typescript
function compare(a: string, b: string): -1 | 0 | 1 {
  return a === b ? 0 : a > b ? 1 : -1;
}
```


# Type Aliases

Type aliases allow you to create reusable names for complex or commonly used types. They simplify your code and make it more readable.

```typescript
type Point = { x: number; y: number };

function printPoint(pt: Point) {
  console.log(`X: ${pt.x}, Y: ${pt.y}`);
}

printPoint({ x: 10, y: 20 });
```

Type aliases can also be used for union types:

```typescript
type ID = number | string;
```

# Type Assertions

Type assertions tell TypeScript to treat a value as a specific type, even if TypeScript can’t infer it. 

This is useful when you know more about the value than TypeScript does.

```typescript
const myCanvas = document.getElementById("main_canvas") as HTMLCanvasElement;
```

Be cautious when using type assertions, as incorrect assertions can lead to runtime errors.