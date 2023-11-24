 #### Solution: Balanced Parentheses
```python
def is_balanced_parentheses(s):
    stack = []
    for char in s:
        if char == '(':
            stack.append(char)
        elif char == ')':
            if not stack:
                return False
            stack.pop()
    return not stack

# Example usage
result = is_balanced_parentheses("((()))")
print(result)  # Output: True 

```