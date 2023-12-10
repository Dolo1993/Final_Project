# TREE
### Definition and Basic Terminology
In Python, a tree is a hierarchical data structure represented using classes and objects. Each element in the tree is a node, and the first node is called the root. Nodes in a tree can have zero or more child nodes, and nodes with no children are referred to as leaves. The relationship between nodes is defined by edges. Nodes in the same level with a common parent are siblings, and the level of a node is determined by its distance from the root. The root has a level of 0, and the height of the tree is the length of the longest path from the root to a leaf.   

#### Basic Terminology:

#### Node
- A fundamental part of a tree, representing a single element.
- Nodes contain data and may have a reference or links to other nodes.
#### Root
- The topmost node in a tree.
- It is the starting point for traversing the tree and has no parent.
#### Leaf
- Nodes with no children; they are at the bottom of the hierarchy.
- Leaves are nodes that do not have any child nodes.
#### Parent
- A node in a tree that has one or more child nodes.
- It is situated closer to the root than its children.
#### Child:
- A node that has a parent node.
- Nodes that are situated further away from the root than their parent.
#### Siblings
- Nodes that share the same parent.
- They are at the same level in the hierarchy.
#### Depth
- The level or distance of a node from the root.
- The root node is at depth 0, and its children are at depth 1, and so on.
#### Height
- The length of the longest path from a node to a leaf.
- The height of a tree is the height of its root node.
#### Subtree
- A tree formed by a node and its descendants. 

 For example let's Consider a simple family tree 
 ``` python  
                       Grandparent
                           |
           +--------------+--------------+
           |                             |
        Parent1                      Parent2
           |                             |
   +-------+-------+             +-------+-------+
   |               |             |               |
 Child1          Child2         Child3          Child4
   |               |             |               |
 +-+-+           +-+-+         +-+-+           +-+-+
 |   |           |   |         |   |           |   |
G1  G2          G3  G4        G5  G6          G7  G8
 |   |           |   |         |   |           |   |
 L1  L2          L3  L4        L5  L6          L7  L8

```
In above diagram, Grandparent is the root, Parent1 and Parent2 are children of Grandparent.
Child1 and Child2 are children of Parent1, and Child3 and Child4 are children of Parent2. G1 to G8 represent the grandchildren, with G1 and G2 being the children of Child1, G3 and G4 being the children of Child2, and so on. Similarly, L1 to L8 represent the great-grandchildren (leaves), with each leaf being a child of a grandchild. 

#### Hierarchy and Relationships in a Tree Structure
In Python, trees can be implemented using classes. Each class represents a node, with attributes such as **data,** **left child,** and **right child.** The hierarchy is maintained through references between nodes, where each node points to its children. The relationships between nodes are crucial for efficient tree traversal and manipulation. Python's object-oriented features make it convenient to create and work with tree structures, allowing for the implementation of various tree-based algorithms and applications. For instance, let's take a look at the below example.

``` python
class TreeNode:
    def __init__(self, data):
        self.data = data
        self.left = None
        self.right = None

# Example of creating a simple binary tree
root = TreeNode(1)
root.left = TreeNode(2)
root.right = TreeNode(3)
root.left.left = TreeNode(4)
root.left.right = TreeNode(5) 

"""In this example, we define a TreeNode class to represent nodes in the tree. We then create a simple binary tree with nodes containing integer values.""" 

```  
``` python 
"""This is how the tree will looks like."""
      1
     / \
    2   3
   / \
  4   5

``` 
#### Types of Trees 
**Binary Trees:** A Tale of Left and Right
Imagine a magical forest where each tree has its own left and right branches, creating a binary world of nodes in Python. In this enchanted land, the BinaryTreeNode class serves as the magical gateway, giving life to each node's data and connecting them through left and right companions. Let's bring this fantasy to life with a simple example:

``` python
class BinaryTreeNode:
    def __init__(self, data):
        self.data = data
        self.left = None
        self.right = None

# Example Binary Tree
#        1
#       / \
#      2   3
#     / \
#    4   5
root = BinaryTreeNode(1)
root.left = BinaryTreeNode(2)
root.right = BinaryTreeNode(3)
root.left.left = BinaryTreeNode(4)
root.left.right = BinaryTreeNode(5) 

``` 
**N-ary Trees:** A Symphony of Children
In the grand orchestra of trees, n-ary trees take center stage, allowing each node to have a myriad of friends (children). The NaryTreeNode class becomes our conductor, orchestrating a symphony of nodes with their unique data and a group of children. let's take a look at the below example:

``` python
class NaryTreeNode:
    def __init__(self, data):
        self.data = data
        self.children = []

# Example n-ary Tree
#        A
#     / | \
#    B  C  D
#   / \
#  E   F
root = NaryTreeNode('A')
root.children = [NaryTreeNode('B'), NaryTreeNode('C'), NaryTreeNode('D')]
root.children[0].children = [NaryTreeNode('E'), NaryTreeNode('F')] 

``` 

**Balanced Trees:** A balanced tree is a type of binary tree in which the depth of the left and right subtrees of any node differ by at most one. The goal of a balanced tree is to ensure that the tree remains reasonably balanced, preventing skewed structures that could degrade the performance of operations like search, insertion, and deletion. Dancing in Harmony Picture a majestic dance floor where trees sway in perfect harmony, their heights differing by at most one branch. Let's view the example below.
```python
# Example Balanced Binary Tree
#        1
#       / \
#      2   3
#     / \
#    4   5
#   /
#  6 

``` 
**An unbalanced tree:** is a binary tree in which the depth of the left and right subtrees of any node can differ significantly, leading to performance issues for certain operations. Unlike balanced trees, unbalanced trees can become skewed or degenerate, resulting in inefficient search, insertion, and deletion operations.

Here's an example of an unbalanced tree:
 ``` python
   1
    \
     2
      \
       3
        \
         4
          \
           5 

"""In this example, the tree is right-skewed, meaning each node only has a right child, and the left subtree is empty.
This type of structure can occur in scenarios where elements are inserted in sorted order.
Unbalanced trees are generally undesirable for search and retrieval operations because they can reduce the advantages of using a binary tree. Trees like AVL trees or Red-Black trees are designed to automatically maintain balance during insertions and deletions, ensuring more consistent performance for various operations."""

``` 
 #### Basic Tree Operations 
**Traversing a Tree:** Dance of In-Order, Pre-Order, and Post-Order
In the magical world of trees, traversing is like dancing through the branches, and Python provides us with a trio of moves: in-order, pre-order, and post-order.

**In-Order Traversal:** Imagine gracefully moving from the leftmost branch to the rightmost, experiencing each node's enchanting data.

``` Python 
class TreeNode:
    def __init__(self, data):
        self.data = data
        self.left = None
        self.right = None

# Example Binary Tree
root = TreeNode(1)
root.left = TreeNode(2)
root.right = TreeNode(3)
root.left.left = TreeNode(4)
root.left.right = TreeNode(5)

def in_order_traversal(node):
    if node:
        in_order_traversal(node.left)
        print(node.data, end=" ")
        in_order_traversal(node.right)

# Example Usage
print("In-Order Traversal:")
in_order_traversal(root)
# Output: 4 2 5 1 3


```
**Pre-Order Traversal:** Now, picture leaping from the root to each subsequent branch, savoring the data as you go.
```python
def pre_order_traversal(node):
    if node:
        print(node.data, end=" ")
        pre_order_traversal(node.left)
        pre_order_traversal(node.right)

# Example Usage
print("Pre-Order Traversal:")
pre_order_traversal(root)
# Output: 1 2 4 5 3


``` 

**Post-Order Traversal:** Finally, visualize reaching the leaves before backtracking, creating a mesmerizing post-order dance.

```python
 def post_order_traversal(node):
    if node:
        post_order_traversal(node.left)
        post_order_traversal(node.right)
        print(node.data, end=" ")

# Example Usage
print("Post-Order Traversal:")
post_order_traversal(root)
# Output: 4 5 2 3 1

```
**Adding and Removing Nodes:** A Symphony of Growth and Pruning
In the ever-evolving tree symphony, adding and removing nodes are like composing new notes and pruning unnecessary ones.

**Adding Nodes:** Envision planting a new colanut in the forest, creating harmonious growth. 

```python
 def add_node(parent, data):
    new_node = TreeNode(data)
    if not parent.left:
        parent.left = new_node
    else:
        parent.right = new_node

# Example Usage
new_data = 7
add_node(root.left, new_data) 


"""Adding Node (7) Diagram:"""
        1
       / \
      2   3
     / \ /
    4   5
       /
      7 (added)

  
 
``` 

**Removing Nodes:** But sometimes, we need to trim the branches to maintain balance. Pruning involves careful removal, much like trimming an overgrown colanut.

```python
 def remove_node(parent, data):
    if parent.left and parent.left.data == data:
        parent.left = None
    elif parent.right and parent.right.data == data:
        parent.right = None

# Example Usage
data_to_remove = 5
remove_node(root.left, data_to_remove)

"""Removing Node (5) Diagram:"""
        1
       / \
      2   3
     / \
    4   5 (Removed)
       /
      7
```
 
#### Practical applications of trees in Python
Let's consider a simplified example where each directory is a node, and subdirectories/files are its children nodes.

```python
 class FileTreeNode:
    def __init__(self, name, is_directory=False):
        self.name = name
        self.is_directory = is_directory
        self.children = []

# Example File System Tree
root_directory = FileTreeNode("Root", is_directory=True)
docs_folder = FileTreeNode("Documents", is_directory=True)
images_folder = FileTreeNode("Images", is_directory=True)
file1 = FileTreeNode("file1.txt")
file2 = FileTreeNode("file2.png")

# Connecting nodes
root_directory.children = [docs_folder, images_folder]
docs_folder.children = [file1]
images_folder.children = [file2]

def list_files(node):
    if node:
        print(node.name)
        if node.is_directory:
            for child in node.children:
                list_files(child)

# Example Usage
print("File System Structure:")
list_files(root_directory)

# Output 
File System Structure:
Root
Documents
file1.txt
Images
file2.png

```
In the above example, the tree represents a file system with a root directory containing "Documents" and "Images" folders, each with their respective files. You can navigate this tree to explore the file structure, manage directories, and perform operations like searching for files or organizing content. Understanding tree traversal becomes key for tasks like listing all files, finding a specific file, or even creating a new directory. 

Click on the [**Problems**](3-link-to-problem.md) to solve individually. However, if you spend more than an hour, feel free to view the solution by clicking on the **Solution** button below the problem.

 