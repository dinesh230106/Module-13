# Exp.No:32  
## CONVERSION OF INFIX TO POSTFIX

---

### AIM  
To write a Python program to convert a given Infix expression to Postfix expression by following the precedence and associative rules. The input expression contains only Division, Subtraction, and Bitwise AND operators. A dictionary is used to set the priority for operators, and a set is used to hold the operators used in the given expression.

---

### ALGORITHM

1. **Start the program.**
2. **Initialize an empty stack** and an empty output string.
3. **Iterate through each character** in the infix expression:
   - If the character is **not an operator**, append it directly to the output string.
   - If the character is an **open parenthesis '('**, push it onto the stack.
   - If the character is a **close parenthesis ')'**, pop from the stack and append to the output until encountering a left parenthesis '('.
   - If the character is an **operator**, handle it based on precedence:
     - While there’s an operator at the top of the stack with higher or equal precedence, pop the stack and append those operators to the output.
     - Push the current operator onto the stack.
4. **Use a priority dictionary** to define operator precedence, ensuring higher precedence operators are placed before lower precedence ones.
5. Once the expression is fully processed, continue popping any remaining operators from the stack and append them to the output.
6. **Return the final postfix expression.**
7. **Print the result.**
8. **End the program.**

---

### PROGRAM

```
# Reg.No: 212223060057
# Name: DINESH KUMAR A
# Program to convert Infix expression to Postfix

def infix_to_postfix(expression):
    precedence = {'/': 3, '-': 2, '&': 1}
    operators = set(['/','-','&'])
    stack = []
    output = ''

    for char in expression:
        if char not in operators and char not in "()":
            output += char
        elif char == '(':
            stack.append(char)
        elif char == ')':
            while stack and stack[-1] != '(':
                output += stack.pop()
            stack.pop()
        else:
            while stack and stack[-1] != '(' and precedence[char] <= precedence[stack[-1]]:
                output += stack.pop()
            stack.append(char)

    while stack:
        output += stack.pop()

    return output


# Example usage
infix_expr = "A/B-C&D"
print("Infix Expression: ", infix_expr)
print("Postfix Expression: ", infix_to_postfix(infix_expr))

```

### OUTPUT
```
Infix Expression:  A/B-C&D
Postfix Expression:  AB/CD-& 

```


### RESULT
Thus, the Python program to convert a given infix expression to postfix form was successfully executed and verified.

