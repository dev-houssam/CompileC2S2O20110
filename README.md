# CompileC2S2O20110
Compile .c to .s to .o to binary Runnable.

### 1. Compilation
GCC follows a multi-step process to convert source code into an executable. These steps are:

1. Preprocessing: Handling preprocessor directives like `#include` and `#define`.
2. Compilation: Translating the preprocessed code into assembly code.
3. Assembly: Converting assembly code into machine code (object files).
4. Linking: Combining object files and libraries to create the final executable.

Let’s explore these steps in detail.

—

### 2. Preprocessing: Expanding Macros and Includes

During preprocessing, the compiler handles directives like `#include` and `#define`. The output is a pure C file with no preprocessor directives.

Command:
```bash
gcc -E main.c -o main.i
```

- -E: Stops after preprocessing.
- main.c: The source file.
- main.i: The output file containing the preprocessed code.

Example:
If `main.c` contains:
```c
	#include <stdio.h>
	#define PI 3.14

	int main() {
	printf(“PI: %f\n”, PI);
	return 0;
}
```
After preprocessing, `main.i` will have the expanded code with the `#include` and `#define` processed.

—

### 3. Compilation: Generating Assembly Code

Command:
```bash
gcc -S main.i -o main.s
```

- -S: Stops after generating assembly code.
- main.s: The output assembly file.

The `main.s` file contains platform-specific assembly instructions that represent your code.

—

### 4. Assembly: Producing Object Files

Command:
```bash
gcc -c main.s -o main.o
```

- -c: Compiles to an object file without linking.
- main.o: The object file, which is a binary representation of the code.

At this stage, the code is not yet executable. It’s a compiled piece waiting to be linked.

—

### 5. Linking: Creating the Executable

Finally, the linker combines object files and libraries into a single executable file.

Command:
```bash
gcc main.o -o main
```

- main: The final executable.

If you have multiple object files (e.g., `main.o` and `utils.o`), you can link them together:
```bash
gcc main.o utils.o -o main
```

—

### 6. One-Step Compilation

GCC also allows you to perform all these steps in one command:
```bash
gcc main.c -o main
```

—

### 7. Debugging with GCC

To enable debugging symbols, use the `-g` flag:
```bash
gcc -g main.c -o main
```
—

### 8. Optimization Levels

You can optimize your code using flags like `-O1`, `-O2`, or `-O3`:
```bash
gcc -O2 main.c -o main
```
- -O1: Basic optimizations.
- -O2: Standard optimizations.
- -O3: Aggressive optimizations.

—

### Conclusion

Voilà ! 

—


Houssam BACAR

