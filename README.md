# COMPILER-DESIGN-BASICS

*COMPANY*: CODETECH IT SOLUTIONS

*NAME*: MADHUKAR KUMAR

*INTERN ID*: CT6WOZM

*DOMAIN*: C++ PROGRAMMING

DURATION: 6 WEEEKS

*MENTOR*: NEELA SANTOSH KUMAR

### **DESCRIPTION**
The given C++ program evaluates a mathematical expression entered by the user. It implements an expression evaluator using the Shunting-Yard algorithm and stacks to handle operator precedence and associativity. The program supports basic arithmetic operations (`+`, `-`, `*`, `/`) along with exponentiation (`^`). Parentheses are also handled to enforce precedence explicitly. Below is a detailed breakdown of the program:

### **Header Files and Namespace**
The program begins by including necessary header files:
- `<cctype>`: For character classification functions.
- `<cmath>`: For mathematical operations (such as exponentiation using `pow`).
- `<iostream>`: For input and output operations.
- `<sstream>`: To parse the input string efficiently.
- `<stack>`: To use stack data structures for operators and operands.
- `<string>`: To manipulate the input expression as a string.

The `using namespace std;` directive is used to avoid prefixing standard library names with `std::`.

### **Function Definitions**
#### `bool isOperator(char c)`
This function checks whether a given character is a valid operator (`+`, `-`, `*`, `/`, `^`). It returns `true` if the character is an operator and `false` otherwise.

#### `int precedence(char op)`
This function determines the precedence level of operators. Operators have different precedence levels:
- `+` and `-` have the lowest precedence (1).
- `*` and `/` have higher precedence (2).
- `^` (exponentiation) has the highest precedence (3).
- If an unrecognized operator is passed, the function returns `0`.

#### `double applyOp(double a, double b, char op)`
This function takes two operands (`a` and `b`) and an operator (`op`). It applies the operator to the operands and returns the computed result. The supported operations are:
- Addition (`+`): `a + b`
- Subtraction (`-`): `a - b`
- Multiplication (`*`): `a * b`
- Division (`/`): `a / b`
- Exponentiation (`^`): `pow(a, b)`

If an invalid operator is encountered, the function returns `0` as a fallback.

### **Main Expression Evaluation Function**
#### `double evaluateExpression(const string& expression)`
This function evaluates the mathematical expression given as a string. It follows these steps:

1. **Initialize Stacks:**
   - `operators`: Stack to store operators.
   - `operands`: Stack to store numerical values.

2. **Tokenize Input:**
   - A `stringstream` object `ss` is used to read tokens from the input string, splitting based on spaces.

3. **Process Each Token:**
   - If the token is a number, it is pushed onto the `operands` stack.
   - If the token is an operator, the program checks precedence and evaluates existing operators in the stack before pushing the new operator.
   - If the token is `(`, it is pushed onto the `operators` stack.
   - If the token is `)`, the program processes all operators until the matching `(` is found.

4. **Process Remaining Operators:**
   - Once all tokens are processed, any remaining operators in the stack are evaluated until the final result is obtained.

### **Main Function**
#### `int main()`
The `main` function performs the following operations:
1. Reads a mathematical expression from the user using `getline(cin, expression);`.
2. Calls `evaluateExpression(expression);` to compute the result.
3. Outputs the computed result using `cout`.
4. Returns `0` to indicate successful execution.

### **Working Example**
#### **Input:**
```
3 + 5 * ( 2 ^ 3 ) - 4 / 2
```
#### **Evaluation Steps:**
1. `2 ^ 3 = 8`
2. `5 * 8 = 40`
3. `3 + 40 = 43`
4. `4 / 2 = 2`
5. `43 - 2 = 41`
#### **Output:**
```
Result: 41
```

### **Key Features**
1. **Operator Precedence Handling:**
   - Ensures correct precedence order (multiplication/division before addition/subtraction, exponentiation is the highest).
2. **Parentheses Support:**
   - Ensures expressions within parentheses are evaluated first.
3. **Stack-Based Evaluation:**
   - Uses stacks to store operators and operands efficiently.
4. **Handles Spaces in Input:**
   - Uses `stringstream` to split tokens based on spaces.

### **Limitations & Improvements**
1. **Unary Operators (`-x`) Not Handled:**
   - The program assumes all numbers are positive or given explicitly.
2. **No Input Validation:**
   - If an invalid expression is entered, the program may produce incorrect results or crash.
3. **Better Number Parsing:**
   - Currently, numbers are extracted based on the first character; improvements can be made for floating-point handling.

### **Conclusion**
This C++ program effectively evaluates mathematical expressions using operator precedence and stacks. By leveraging `stringstream` for tokenization and stacks for evaluation, it ensures proper execution of complex expressions. It serves as a foundation for building more advanced expression evaluators or calculators in C++.

### **IMAGE**

![Image](https://github.com/user-attachments/assets/c5b8e254-8364-4671-9c42-7c306c60bf55)



