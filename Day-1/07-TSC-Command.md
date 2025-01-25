# Common TSC Commands

- `tsc --init`: Generates a tsconfig.json file with recommended settings in the working directory, which can be customized for your project.

- `tsc`: Compiles the entire project based on the settings defined in the tsconfig.json file located in the working directory.

- `tsc app.ts util.ts`: Compiles only the specified files (app.ts and util.ts), ignoring the tsconfig.json file and using the default compiler options.

- `tsc --watch` or `tsc -w`: This command watches the input files for changes and recompiles them automatically whenever a change is detected.

- `tsc --version` or `tsc -v`: This command prints the version of the TypeScript compiler that is currently installed.
