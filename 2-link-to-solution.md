``` python
def count_unique_elements(input_list):
    unique_elements = set()
    for element in input_list:
        unique_elements.add(element)
    return len(unique_elements)

# Example Usage
numbers = [1, 2, 3, 4, 2, 3, 5, 6, 7, 8, 1]
result = count_unique_elements(numbers)
print(result)
# Output: 8 

```