# Exp.No:34  
## PREFIX EVALUATION

---

### AIM  
To write a Python program to evaluate a user-given Prefix expression using a stack. The expression must contain operators such as Multiplication, Addition, and Subtraction.

---

### ALGORITHM

1. **Start the program.**
2. Define a set of valid operators: `*, -, +, %, /, **`.
3. Initialize an empty stack.
4. Traverse the prefix expression from **right to left**:
   - If the character is a **digit**, convert it to an integer and push it onto the stack.
   - If the character is an **operator**, pop two elements from the stack.
     - Apply the operator on the two popped operands.
     - Push the result back onto the stack.
   - If an invalid character is encountered, raise an error.
5. After traversal, the stack should contain only **one element**.
6. Return the **single element** as the evaluation result.
7. **End the program.**

---

### PROGRAM

```
# Reg.No: 212223060057
# Name: DINESH KUMAR A
# Program to evaluate a Prefix Expression using Stack

OPERATORS = set(['*', '+', '-', '/', '%', '**'])

def evaluate_prefix(expression):
    stack = []
    # Traverse from right to left
    for item in reversed(expression):
        if item not in OPERATORS:
            stack.append(int(item))
        else:
            a = stack.pop()
            b = stack.pop()
            if item == '+':
                result = a + b
            elif item == '-':
                result = a - b
            elif item == '*':
                result = a * b
            elif item == '/':
                result = a / b
            elif item == '%':
                result = a % b
            elif item == '**':
                result = a ** b
            stack.append(result)
    return stack[0]

# Input from user
exp = input("Enter the prefix expression separated by spaces: ").split()

print("Prefix Expression:", exp)
print("Evaluated Result:", evaluate_prefix(exp))


```


### OUTPUT
```
Enter the prefix expression separated by spaces: + 5 * 3 2
Prefix Expression: ['+', '5', '*', '3', '2']
Evaluated Result: 11

```



### RESULT
Thus, the Python program to evaluate a Prefix expression using a stack has been successfully executed and verified.
