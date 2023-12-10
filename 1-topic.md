# 1. Stack

###  Introduction to Stack
In Python, a **stack** is a vital data structure operating on the Last In, First Out (LIFO) principle, signifying that the most recently added element is the first to be removed. Picture a stack as a vertical arrangement of elements, akin to a stack of plates, where items are added or removed solely from the top. The stack revolves around two fundamental operations: "Push," involving adding an element to the top, and "Pop," involving the removal of the top element. With a top and a bottom, symbolizing the most recent and longest-standing elements, respectively, stacks in Python are frequently implemented using lists. They play a pivotal role in computer science applications like function call management, expression evaluation, and software undo mechanisms, establishing them as a fundamental concept in programming. Python's stack operations exhibit high efficiency, often with a time complexity of O(1), underscoring their importance in algorithmic design and problem-solving within Python programming and computer science at large.

A stack consists of elements with two primary operations: **Push** (adding an element to the stack) and **Pop** (removing the top element from the stack).

 ### Basic Operations

#### 1. Push Operation

Pushing in a stack is comparable to stacking plates in real life. Imagine placing one plate on top of another – the most recently added plate is the first one you can pick up. In Python programming Language we use use the key word **append** to add or push an item to the stack,and the Push operation involves adding an element to the top of the stack. For instance:

```python
stack = []      # Creating an empty stack
stack.append(1)  # Pushing 1 onto the stack
stack.append(2)  # Pushing 2 onto the stack
stack.append(3)  # Pushing 3 onto the stack  
The output of this stack are #[1, 2, 3] 

Initial Stack: []
--------------
|            |
|            |
|            |
--------------

After stack.append(1):
--------------
|     1      |
--------------
|            |
|            |
--------------

After stack.append(2):
--------------
|     2      |
--------------
|     1      |
--------------
|            |
--------------

After stack.append(3):
--------------
|     3      |
--------------
|     2      |
--------------
|     1      |
-------------- 

```  
#### 2. Pop operation 
The "pop" operation in the context of a stack refers to the removal of the topmost element from the stack. In Python, the "pop" method is used to implement this operation on a list acting as a stack. When you invoke "pop" on a stack, it not only removes the top element but also returns the value of the removed element. For instance, consider a stack initialized as stack = [1, 2, 3]. If you execute stack.pop(), the operation will remove the element 3 from the top of the stack, and the updated stack will be [1, 2]. Additionally, the "pop" method returns the value 3, which was removed. This exemplifies the Last In, First Out (LIFO) behavior of a stack, as the most recently added element is the first one to be removed. Carefully view the example below and seehow the **pop** operation works.  

``` python 
# Creating a stack
stack = [1, 2, 3]

# Displaying the original stack
print("Original Stack:", stack)

# Using pop to remove and retrieve the top element
removed_element = stack.pop()

# Displaying the updated stack and the removed element
print("Updated Stack:", stack)
print("Removed Element:", removed_element)
Original Stack: #[1, 2, 3]  
Updated Stack: #[1, 2]
Removed Element: # 3  

# Diagram
Original Stack: [1, 2, 3]
-------------------------
|           3           |
-------------------------
|           2           |
-------------------------
|           1           |
-------------------------

After stack.pop():
Updated Stack: [1, 2]
-------------------------
|           2           |
-------------------------
|           1           |
-------------------------

Removed Element: 3

``` 
#### 3. Implementation in Python 
In Python, implementing a stack can be achieved using built-in data structures such as lists or collections. To create a stack using lists, you can initialize an empty list and use the "append" method to add elements to the top of the stack. For example, stack = [] creates an empty stack, and stack.append(1) pushes the element 1 onto the stack. The "pop" operation is then employed to remove and retrieve the top element. Continuing the example, if you execute stack.pop(), it will remove the most recently added element, and you can subsequently perform additional "push" and "pop" operations as needed. Collections like the deque class from the collections module can also be employed to implement a stack with efficient push and pop operations. The following demonstrates the basic implementation: 

```python
# Creating a stack using a list
stack = []   #output is empty because notthing have been added to the list

# Pushing elements onto the stack
stack.append(1)
stack.append(2)
stack.append(3) 

# Displaying the stack after push operations
print("Stack after push operations:", stack) #output is [1,2,3]

# Popping the top element from the stack
popped_element = stack.pop() # 3 is removed, always remember LIFO

# Displaying the updated stack and the popped element
print("Updated Stack:", stack) #output is [1,2]
print("Popped Element:", popped_element) #output is [3]

```
#### 3. Use Cases  
Stacks find practical application in various scenarios across computer science and programming due to their Last In, First Out (LIFO) nature. One common use case is in function call management, where the call stack keeps track of function calls and their local variables. When a function is called, its context is pushed onto the stack, and when the function completes, its context is popped off. This ensures proper execution flow and memory management. Another application is in the undo mechanism of software, where each action performed is pushed onto a stack, allowing users to undo operations in reverse order. Additionally, expression evaluation, such as arithmetic expressions or parsing, often employs stacks to manage operators and operands. In a specific problem scenario, consider the task of checking the balanced parentheses in an expression. A stack can be used to keep track of opening and closing parentheses, ensuring that they occur in the correct order. If, after parsing the expression, the stack is empty, it indicates a balanced set of parentheses; otherwise, it signals an imbalance. This exemplifies how stacks provide an efficient solution to ensure the correctness of nested structures in various programming tasks.   

#### 4. problem to solve
Let's consider the problem of checking whether a given expression has balanced parentheses using a stack in Python. The idea is to iterate through each character in the expression, pushing opening parentheses onto the stack and popping when a closing parenthesis is encountered. At the end of the iteration, if the stack is empty, the parentheses are balanced; otherwise, there is an imbalance.  

``` Python
def is_balanced_parentheses(expression):
    stack = []
    opening_brackets = {'(', '[', '{'}
    closing_brackets = {')': '(', ']': '[', '}': '{'}

    for char in expression:
        if char in opening_brackets:
            stack.append(char)
        elif char in closing_brackets:
            if not stack or stack.pop() != closing_brackets[char]:
                return False

    return not stack  # If stack is empty, parentheses are balanced

# Example usage
expression1 = "((a + b) * (c - d))"
expression2 = "({[a + b]})"
expression3 = "((a + b) * (c - d}"

print(is_balanced_parentheses(expression1))  # Output: True
print(is_balanced_parentheses(expression2))  # Output: True
print(is_balanced_parentheses(expression3))  # Output: False

```  

In Python, a stack is a fundamental data structure operating on the Last In, First Out (LIFO) principle. Conceptually visualized as a vertical collection, items are added or removed exclusively from the top. Stacks in Python are commonly implemented using lists and play a crucial role in computer science applications such as function call management, expression evaluation, and software undo mechanisms. The efficiency of push and pop operations is typically high, emphasizing the significance of stacks in algorithmic design. 

 Click on the [**Problems**](link-to-problem.md) to solve individually. However, if you spend more than an hour, feel free to view the solution by clicking on the **Solution** button below the problem.
