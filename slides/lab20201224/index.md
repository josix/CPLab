---
marp: true
title: Computer Programming 1 Lab - Lecture 13
date: 2020-12-24
paginate: true 
---
<style>
img[alt~="center"] {
  display: block;
  margin: 0 auto;
}
</style>
# Computer Programming 1 Lab
## 2020-12-24
Chang, Chi-Hung

---

# Outline
- Stack
- Queue
- Tree
- Exercise 12

---

# Stack
- Last In, First Out (LIFO)
- Operations
    - push
    - pop

---

# Stack
![w:9in center](../assets/stack.png)

---

# Queue
- First In, First Out (FIFO)
- Operations
    - enqueue
    - dequeue

---

# Queue
![w:8in center](../assets/Data_Queue.svg)

---

# Tree
- Parent & child
- A parent can have more than one child
- All nodes are connected by pointers
- A node with no child is called **leaf**

---

# Tree
## Binary Tree
The most common tree that for any parents, there will be at most 2 children
![w:4in center](../assets/Binary_tree.svg)

---

# Tree
## Tree Structure
```c
struct node{
    int value;
    struct node* left;
    struct node* right;
}

struct node* root = malloc(sizeof(struct node));
```

---

# Tree
## Insertion
Suppose $A$ is a node that we are going to insert a new node $B$ to its left child.
```c
struct node* B = malloc(sizeof(struct node));
B->left = NULL;
B->right = NULL;
A->left = B;
```

---

# Tree
## Deletion
Suppose we want to remove $A$'s left node.
```c
free(A->left);
A->left = NULL;
```

---

# Tree
## Tree Order
### Inorder
Order: **left $\to$ root $\to$ right**
![w:3in center](../assets/Binary_search_tree.svg)
$1 \to 3 \to 4 \to 6 \to 7 \to 8 \to 10 \to 13 \to 14$

---

# Tree
## Tree Order
### Preorder
Order: **root $\to$ left $\to$ right**
![w:3in center](../assets/Binary_search_tree.svg)
$8 \to 3 \to 1 \to 6 \to 4 \to 7 \to 10 \to 14 \to 13$

---

# Tree
## Tree Order
### Postorder
Order: **left $\to$ right $\to$ root**
![w:3in center](../assets/Binary_search_tree.svg)
$1 \to 4 \to 7 \to 6 \to 3 \to 13 \to 14 \to 10 \to 8$

---

# Exercise 12
Give you a binary tree that contains numbers of nodes. The value of each node is a unique positive integer. Please print out the tree in **postorder**.
- Input
    ```
    8 left 3
    8 right 10
    3 left 1
    3 right 6
    6 left 4
    6 right 7
    10 right 14
    14 left 13
    ```
- Output
    ```
    1 4 7 6 3 13 14 10 8
    ```

---
<!-- 
  backgroundImage: "linear-gradient(to bottom, #67b8e3, #0288d1)"
-->
<style scoped>
  h1, h2, {
    color: #efefef;
  }
</style>
# <!--fit--> Any Question?
