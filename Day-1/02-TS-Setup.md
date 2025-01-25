To start using TypeScript effectively, you need to set up its compiler, known as `tsc`. This tool allows you to `write TypeScript code and transform it into plain JavaScript`.

Let’s break down the process step by step, including useful commands and examples.

# Installing TypeScript

To use TypeScript, you need to install the compiler, `tsc`. This can be done globally or locally using `npm`.

## Global Installation

Install TypeScript globally on your system:

```bash
npm install -g typescript
```

- The `-g` flag ensures that `tsc` is accessible from any directory on your machine.
- After installation, confirm it works by checking the version:
  ```bash
  tsc --version
  ```

## Local Installation (Optional)

You can install TypeScript locally to keep it tied to a specific project:

```bash
npm install typescript --save-dev
```

The `--save-dev` flag ensures that TypeScript is added to your project's `devDependencies` in `package.json`.

Once TypeScript is installed locally, you can access the `tsc` compiler via `npx`:

```bash
npx tsc <filename>.ts
```

`npx` runs the locally installed version of TypeScript from the `node_modules` folder. This avoids the need for a global installation of TypeScript.

# Initializing a TypeScript Project

A TypeScript project can be managed effectively with a `tsconfig.json` file. This configuration file specifies `how TypeScript should compile your code`.

## Creating tsconfig.json file

Run the following command to initialize a new TypeScript project:

```bash
tsc --init
```

This generates a `tsconfig.json` file with default settings.

You can customize this file to:

- Specify input and output directories.
- Enable strict type-checking.
- Set compiler options like `target` JavaScript version, module system, and more.

# Writing Your First TypeScript File

1. **Create a File:** In an empty directory, create a new file named `index.ts`:

   ```typescript
   // A simple program that prints a greeting.
   console.log("Hello, TypeScript!");
   ```

2. **Compile the File:** Run the `tsc` command to compile the TypeScript file:

   ```bash
   tsc index.ts
   ```

3. **Result:**
   - A new file named `index.js` will be generated in the same directory.
   - The `index.js` file contains JavaScript code that can be run in any JavaScript environment.

# Compiling Files with a `tsconfig.json` File

When using a `tsconfig.json`, you don’t need to specify individual files for compilation. TypeScript will automatically compile all files that match the configuration.

1. **Compile All Files:** Run `tsc` in a directory with a `tsconfig.json` file:

   ```bash
   tsc
   ```

2. **Compile in Watch Mode:** Use the `--watch` flag to automatically recompile files whenever changes are detected:
   ```bash
   tsc --watch
   ```

# Useful TypeScript Commands

| Command             | Description                                                          |
| ------------------- | -------------------------------------------------------------------- |
| `tsc <filename>.ts` | Compiles a single TypeScript file into JavaScript.                   |
| `tsc --init`        | Generates a `tsconfig.json` file for your project.                   |
| `tsc`               | Compiles all TypeScript files in the directory with `tsconfig.json`. |
| `tsc --watch`       | Watches for file changes and re-compiles automatically.              |
