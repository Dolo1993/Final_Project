### Problem
Imagine you are building a tool to calculate the total size of a directory and its subdirectories. Your goal is to implement a Python function that takes a directory node as input and returns the total size of that directory and all its contents. Each file or folder is represented by a FileTreeNode class, which has a size attribute for files.


```Python 
class FileTreeNode:
    def __init__(self, name, is_directory=False, size=0):
        self.name = name
        self.is_directory = is_directory
        self.size = size
        self.children = [] 

def calculate_directory_size(node):
    # Your implementation here 


# Example File System Tree
root_directory = FileTreeNode("Root", is_directory=True)
docs_folder = FileTreeNode("Documents", is_directory=True)
images_folder = FileTreeNode("Images", is_directory=True)
file1 = FileTreeNode("file1.txt", size=1024)
file2 = FileTreeNode("file2.png", size=2048)

# Connecting nodes
root_directory.children = [docs_folder, images_folder]
docs_folder.children = [file1]
images_folder.children = [file2]

# Expected Output
total_size = calculate_directory_size(root_directory)
print(f"Total Size of the Directory: {total_size} bytes")

"""Total Size of the Directory: 3072 bytes"" 

```

[Click here for the solution](3-link-to-solution.md)