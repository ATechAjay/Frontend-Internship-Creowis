Click [here](./04-TS-Practice.ts) for solution!

# Working with Primitives

- Declare variables for each primitive type (`string`, `number`, and `boolean`) and assign appropriate values.
- Write a function `isEven` that takes a `number` and returns `true` if it’s even and `false` otherwise.

# 2. Arrays and Type Safety

- Create an array of numbers and a separate array of strings using both `type[]` and `Array<type>` syntax.
- Write a function `getFirstElement` that accepts an array of any type and returns its first element.

# 3. Tuples and Fixed Length Data

- Define a tuple to represent a user's profile: `[username: string, age: number, isAdmin: boolean]`.
- Write a function `printUserProfile` that takes this tuple and logs a formatted message like:  
  `Username: Alice, Age: 30, Admin: true`.

# 4. Using the `any` Type

- Create a variable of type `any` and assign it different types of values (string, number, object).
- Write a function that takes an `any` type parameter, logs its value, and changes its type during the function execution.

# 5. Type Annotations in Functions

- Write a function `multiply` that takes two numbers as parameters and returns their product. Use type annotations.
- Create another function `greetUser` that takes a name (string) and returns a greeting message. Include both parameter and return type annotations.

# 6. Functions Returning Promises

- Create an asynchronous function `fetchMessage` that returns a `Promise<string>`. Simulate fetching a message and return a string after 2 seconds.

# 7. Object Types and Optional Properties

- Define a type for a `Car` object with the following properties:
  - `make` (string)
  - `model` (string)
  - `year` (number)
  - `isElectric` (optional, boolean)
- Write a function `printCarInfo` that takes a `Car` object and logs its details. If `isElectric` is undefined, log a default message.

# 8. Union Types and Literal Types

- Write a function `formatInput` that accepts either a string or a number:
  - If it’s a string, return it in uppercase.
  - If it’s a number, return it rounded to the nearest integer.
- Create a function `setAlignment` that accepts a parameter of type `"left" | "center" | "right"` and logs the chosen alignment.

# 9. Type Aliases

- Create a type alias `Rectangle` to represent an object with properties: `width` and `height` (both numbers).
- Write a function `calculateArea` that takes a `Rectangle` and returns its area.

# 10. Type Assertions

- Use `document.getElementById` with a type assertion to get an `HTMLInputElement`, then set its `value` property to `"Hello TypeScript"`.
- Create a function `getCanvasElement` that asserts the type of a DOM element to `HTMLCanvasElement` and logs its dimensions (`width` and `height`).
