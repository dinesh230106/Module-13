# Exp.No:33  
## POSTFIX EVALUATION

---

### AIM  
To write a Python program to evaluate a user-given Postfix expression that contains Multiplication and Addition operators using the stack concept.

---

### ALGORITHM

1. **Start the program.**
2. Define a set named `OPERATORS` containing all the valid operators: `*, +, **, -, /, %`.
3. Define a function `evaluate_postfix(exp)` to evaluate the postfix expression:
   - Inside the function, create an empty list called `stack` to store operands and intermediate results.
4. Loop through each item in the given postfix expression:
   - If the current item is **not in OPERATORS**, it is an operand, so append it to the stack.
   - If the current item is an **operator**:
     - Pop the top two elements from the stack (first pop is `a`, second pop is `b`).
     - Perform the operation `b <operator> a` depending on the current operator.
     - Store the result in a variable called `result`.
     - Append the result back to the stack.
5. After the loop ends, return the first element of the stack as the final evaluation result.
6. Take a postfix expression as input from the user.
7. Print the postfix expression.
8. Call the function `evaluate_postfix()` with the input and print the result.
9. **End the program.**

---

### PROGRAM

```
# Reg.No: 212223060057
# Name: DINESH KUMAR A
# Program to evaluate a Postfix Expression using Stack

OPERATORS = set(['*', '+', '-', '/', '%', '**'])

def evaluate_postfix(exp):
    stack = []
    for item in exp:
        if item not in OPERATORS:
            stack.append(int(item))
        else:
            a = stack.pop()
            b = stack.pop()
            if item == '+':
                result = b + a
            elif item == '-':
                result = b - a
            elif item == '*':
                result = b * a
            elif item == '/':
                result = b / a
            elif item == '%':
                result = b % a
            elif item == '**':
                result = b ** a
            stack.append(result)
    return stack[0]

# Input from user
exp = input("Enter the postfix expression separated by spaces: ").split()

print("Postfix Expression:", exp)
print("Evaluated Result:", evaluate_postfix(exp))


```

### OUTPUT
```
Enter the postfix expression separated by spaces: 5 3 + 2 *
Postfix Expression: ['5', '3', '+', '2', '*']
Evaluated Result: 16

```


### RESULT
Thus, the Python program to evaluate a Postfix expression using the stack concept was successfully executed and verified.

