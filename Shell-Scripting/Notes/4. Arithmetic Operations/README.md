### Arithmetic Operations in Shell Scripting

#### Definition:
Arithmetic operations in shell scripting involve performing mathematical calculations on numerical values. Shell scripting provides built-in mechanisms for addition, subtraction, multiplication, division, and more.

#### Arithmetic Operators:
1. **Addition (+)**: Adds two numbers.
2. **Subtraction (-)**: Subtracts one number from another.
3. **Multiplication (*)**: Multiplies two numbers.
4. **Division (/)**: Divides one number by another.
5. **Modulus (%)**: Returns the remainder of a division.
6. **Increment (++)**: Increases the value of a variable by 1.
7. **Decrement (--)**: Decreases the value of a variable by 1.

#### Syntax:
- Arithmetic operations can be performed using the `expr` command or using double parentheses `((...))`.
- Example:
  ```bash
  # Using expr command
  result=$(expr $num1 + $num2)
  
  # Using double parentheses
  result=$((num1 + num2))
  ```

#### Example Shell Script with Arithmetic Operations:
```bash
#!/bin/bash

# Define variables
num1=10
num2=5

# Perform arithmetic operations
sum=$((num1 + num2))
difference=$((num1 - num2))
product=$((num1 * num2))
quotient=$((num1 / num2))
remainder=$((num1 % num2))

# Display results
echo "Sum: $sum"
echo "Difference: $difference"
echo "Product: $product"
echo "Quotient: $quotient"
echo "Remainder: $remainder"
```

#### Important Notes:
- Arithmetic operations in shell scripting are performed using operators like `+`, `-`, `*`, `/`, `%`, `++`, and `--`.
- Use either the `expr` command or double parentheses `((...))` to perform arithmetic operations.
- Variables used in arithmetic operations should contain numerical values only.

#### Summary:
Arithmetic operations in shell scripting allow you to perform mathematical calculations on numerical values. Whether it's addition, subtraction, multiplication, or division, understanding arithmetic operators and syntax is essential for writing scripts that manipulate numerical data.