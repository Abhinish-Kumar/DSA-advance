


# Tree

https://www.programiz.com/dsa/binary-tree


 ## What is a tree?
Tree:-  A tree is a collection of nodes connected by edges. It starts with a root node and expands into a hierarchy where each node can have zero or more children. Unlike graphs, trees have no cycles, and there's exactly one path between any two nodes.

### Tree Structure in Computer Science: 
1. A tree is an abstract data type (ADT) that represents a hierarchical structure with connected nodes.
2. Each node is connected to exactly one parent, except for the root node, which has no parent.
3. Trees do not contain cycles or loops, meaning no node can be its own ancestor.



## History of tree Data Strucute?
While the concept of trees can be traced back to early mathematical work by Arthur Cayley, the formalization and application of tree data structures in computer science were contributions from multiple researchers in the 1950s and 1960s. Notable contributors include George Collins for binary search trees, J. W. J. Williams for heaps, and Georgy Adelson-Velsky and Evgenii Landis for AVL trees.



## Types of tree and their use

| **Tree Data Structure**                            | **Percentage of Use** |
|----------------------------------------------------|-----------------------|
| **Binary Trees**                                   | **~50%**              |
| - Binary Search Tree (BST)                         |                       |
|   - Self-Balancing BST (e.g., AVL Tree, Red-Black) |                       |
| - Full Binary Tree                                 |                       |
| - Complete Binary Tree                             |                       |
| - Perfect Binary Tree                              |                       |
| **Binary Heap**                                    | **~20%**              |
| - Min-Heap                                         |                       |
| - Max-Heap                                         |                       |
| **B-Trees**                                        | **~10%**              |
| - B-Tree                                           |                       |
| - B+ Tree                                          |                       |
| **Trie (Prefix Tree)**                             | **~8%**               |
| **Segment Tree**                                   | **~5%**               |
| **Fenwick Tree (Binary Indexed Tree)**             | **~3%**               |
| **Quad Tree**                                      | **~2%**               |
| **K-D Tree**                                       | **~1%**               |
| **Suffix Tree**                                    | **~1%**               |
| **N-ary Tree**                                     | **~<1%**              |
| **Radix Tree**                                     | **~<1%**              |

















## Key Terms.

1. Node: The fundamental unit of a tree. Each node contains a value or data and may link to other nodes (its children).
2. Root: The topmost node in a tree, from which all other nodes descend.
3. Edge: The connection between a parent and a child node.
4. Leaf: A node with no children.
5. Subtree: Any node along with its descendants.
6. Depth/Level: The number of edges from the root to the node.
7. Height: The number of edges on the longest path from a node to a leaf.

## Properties of Trees

1. Acyclic: Trees do not contain any cycles.
2. Connected: All nodes are connected via edges.
3. Nodes may have multiple children depending on the type of tree.
4. Each child can be treated as the root of its own subtree, making recursion useful for tree traversal.
5. Trees differ from linear data structures, as they cannot always be represented in a single straight line.


## Why tree

Other data structures such as arrays, linked list, stack, and queue are linear data structures that store data sequentially. In order to perform any operation in a linear data structure, the time complexity increases with the increase in the data size. But, it is not acceptable in today's computational world.

Different tree data structures allow quicker and easier access to the data as it is a non-linear data structure.






## Other resources to learn

| Week | Topic                                      | Description                                                                                        | Resources/References                                         |
|------|--------------------------------------------|----------------------------------------------------------------------------------------------------|--------------------------------------------------------------|
| 1    | Introduction to Trees                      | Understand the basics of trees, including terminology and the importance of trees in data structures. | [GeeksforGeeks: Tree Data Structure](https://www.geeksforgeeks.org/binary-tree-data-structure/) |
| 2    | Binary Tree Basics                         | Learn the specific characteristics of binary trees, including node structure and tree properties.   | [Programiz: Binary Tree](https://www.programiz.com/dsa/binary-tree) |
| 3    | Binary Tree Traversal                      | Explore different traversal methods like Inorder, Preorder, and Postorder.                         | [GeeksforGeeks: Tree Traversal](https://www.geeksforgeeks.org/tree-traversals-inorder-preorder-and-postorder/) |
| 4    | Binary Search Tree (BST)                   | Understand BST properties and how they differ from binary trees.                                    | [GeeksforGeeks: Binary Search Tree](https://www.geeksforgeeks.org/binary-search-tree-data-structure/) |
| 5    | Tree Insertion and Deletion                | Learn how to insert and delete nodes in both binary trees and binary search trees.                  | [Programiz: BST Insertion and Deletion](https://www.programiz.com/dsa/binary-search-tree) |
| 6    | Balanced Trees (AVL and Red-Black Trees)   | Study advanced binary trees like AVL and Red-Black Trees, focusing on balancing techniques.         | [GeeksforGeeks: Balanced Trees](https://www.geeksforgeeks.org/balanced-binary-tree/) |
| 7    | Binary Tree Applications                   | Learn about the applications of binary trees in various algorithms and real-world problems.         | [Topcoder: Binary Tree Applications](https://www.topcoder.com/thrive/articles/binary-trees-data-structures) |
| 8    | Advanced Problems and Optimization         | Solve complex binary tree problems and learn optimization techniques for large datasets.            | [LeetCode: Binary Tree Problems](https://leetcode.com/tag/binary-tree/) |

















