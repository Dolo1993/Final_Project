```Python 
def calculate_directory_size(node):
    if not node:
        return 0

    total_size = node.size

    if node.is_directory:
        for child in node.children:
            total_size += calculate_directory_size(child)

    return total_size 
    
```