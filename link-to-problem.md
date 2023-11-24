 ``` Python
    def __init__(self):
        self.items = []

    def push(self, item):
        self.items.append(item)


def is_balanced_parentheses(s: str) -> bool:
    """
    Parameters:
    - s (str): The input string.

    Returns:
    - bool: True if parentheses are balanced, False otherwise.
    """
    # Your implementation here

result = is_balanced_parentheses("((()))")
print(result)  # Output: True

result = is_balanced_parentheses("(()")
print(result)  # Output: False 

```
[Click here for the solution](link-to-solution.md)

