# Exp.No:31  
## IMPLEMENTATION OF STACK

---

### AIM  
To write a Python program to implement a stack using a list and its built-in methods (`append()`, `pop()`).

---

### ALGORITHM

1. **Start the program.**
2. **Define a class `st`** with the following methods:
   - `push(self, num)`: Adds the number `num` to the stack.
   - `pop(self)`: Removes and returns the top element from the stack.
3. **Create a stack object `s`** using the class `st`.
4. **Input the stack size**: Take an integer input `size` to define the size of the stack.
5. **Loop through numbers from 1 to size**: Add only the odd numbers to the stack using the `push()` method.
6. **Display the elements** in the stack after the loop completes.
7. **Call `pop()`** to remove the top element from the stack and display the popped element.
8. **Display the stack again** to show the remaining elements.
9. **End the program.**

---

### PROGRAM

```
# Reg.No: 212223060057
# Name: DINESH KUMAR A
# Program to implement Stack using list

class st:
    def __init__(self):
        self.stack = []

    def push(self, num):
        self.stack.append(num)

    def pop(self):
        if len(self.stack) == 0:
            return "Stack is empty!"
        else:
            return self.stack.pop()

# Create stack object
s = st()

# Input stack size
size = int(input("Enter the size of the stack: "))

# Push odd numbers into the stack
for i in range(1, size + 1):
    if i % 2 != 0:
        s.push(i)

print("Stack elements after pushing odd numbers:", s.stack)

# Pop the top element
popped = s.pop()
print("Popped element:", popped)

# Display remaining stack elements
print("Stack after popping:", s.stack)

```
OUTPUT
```
Enter the size of the stack: 7
Stack elements after pushing odd numbers: [1, 3, 5, 7]
Popped element: 7
Stack after popping: [1, 3, 5]

```

RESULT

Thus, the Python program to implement a stack using a list was successfully executed and verified.
