# Numeric Expression Evaluator in C

This project implements a numeric expression evaluator in C language. It is capable of converting expressions from infix to postfix notation (Reverse Polish Notation - RPN) and calculating the numerical value of these expressions. The project makes extensive use of the Stack data structure to manage operators and operands during the conversion and evaluation processes.

## Features

*   **Infix to Postfix Conversion**: Transforms mathematical expressions from the usual form (infix) to postfix notation.
*   **Postfix to Infix Conversion**: Reconstructs the infix expression from its postfix form, adding parentheses when necessary to maintain correct precedence.
*   **Postfix Expression Evaluation**: Calculates the numerical value of expressions in postfix notation.
*   **Infix Expression Evaluation**: Calculates the numerical value of expressions in infix notation, using internal conversion to postfix.
*   **Support for Basic Operators**: Addition (`+`), Subtraction (`-`), Multiplication (`*`), Division (`/`), Modulo (`%`), Exponentiation (`^`).
*   **Support for Mathematical Functions**: Square root (`raiz`), Sine (`sen`), Cosine (`cos`), Tangent (`tg`), Base-10 logarithm (`log`).

## Project Structure

 The project consists of the following files:

*   `expressao.h`: Contains the definitions of the `Expressao` structure and the prototypes of the conversion and evaluation functions.
*   `expressao.c`: Implements the functions declared in `expressao.h`, including the logic for stack manipulation, notation conversion, and expression evaluation.
*   `main.c`: Contains the main function (`main`) that demonstrates the use of the evaluator's functionalities through a series of tests with different expressions.

## How to Compile

To compile the project, you will need a C compiler (such as GCC). Navigate to the project's root directory in your terminal and execute the following command:

```bash
gcc main.c expressao.c -o evaluator -lm
```

*   `gcc`: The C compiler.
*   `main.c expressao.c`: The source files to be compiled.
*   `-o evaluator`: Defines the output executable name as `evaluator`.
*   `-lm`: Links the math library (necessary for functions like `sqrt`, `sin`, `cos`, `tan`, `log10`, `pow`, `fmod`).

## How to Run

After successful compilation, you can run the program from the terminal:

```bash
./evaluator
```

The program will display the results of the predefined tests in the `main.c` file, showing the infix expressions, their conversions to postfix, the reconstruction to infix, and the calculated values.

## Example Usage (from `main.c`)

```c
#include <stdio.h>
#include <string.h>
#include <math.h>
#include "expressao.h"

int main() {
    Expressao exp;
    printf("=== Expression Evaluator ===\n\n");

    // Test 1
    strcpy(exp.inFixa, "(3 + 4) * 5");
    strcpy(exp.posFixa, getFormaPosFixa(exp.inFixa));
    printf("Infix: %s\n", exp.inFixa);
    printf("Postfix: %s\n", exp.posFixa);
    printf("Converted Infix: %s\n", getFormaInFixa(exp.posFixa));
    printf("Value (postfix): %.5f\n", getValorPosFixa(exp.posFixa));
    printf("Value (infix): %.5f\n", getValorInFixa(exp.inFixa));
    printf("------------------------------------------------------------\n");

    // Other tests...

    printf("=== End of tests ===\n");
    return 0;
}
```

## Contribution

Contributions are welcome! Feel free to open issues or submit pull requests for improvements, bug fixes, or new features.

## License

This project is licensed under the [MIT License](https://opensource.org/licenses/MIT).

