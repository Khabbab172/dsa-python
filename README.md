# Data Structures & Algorithms – Practice Notebook

This repository is a **hands-on DSA notebook** where each concept is implemented from scratch in Python. The goal is **clarity over cleverness**: build intuition, understand internal mechanics, and practice problem-solving patterns.

Below is a topic-by-topic explanation of what’s covered and *why each thing matters*.

---

## 1. Recursion Fundamentals

You’ll find multiple small recursive functions such as:

* Printing numbers
* Passing parameters that change on each call
* Understanding **base case vs recursive case**

### Example

```python
def print_numbers(n):
    if n == 0:
        return
    print(n)
    print_numbers(n - 1)
```

**Key idea**: every recursive function must move toward a base case.

**Why this matters**
Recursion is the backbone of trees, graphs, divide-and-conquer, and DP. These examples build intuition about:

* Call stack behavior
* Order of execution (top-down vs bottom-up)
* Parameter evolution

---

## 2. Stack

Implemented a custom `Stack` class with operations like:

* push
* pop
* peek

### Example

```python
class Stack:
    def __init__(self):
        self.items = []

    def push(self, x):
        self.items.append(x)

    def pop(self):
        return self.items.pop() if self.items else None
```

### Related Problems

* **Valid Parenthesis**
* **Stock Span Problem**

**Why this matters**
Stacks are used when:

* You need *last-in-first-out* behavior
* Solving expression parsing
* Backtracking and undo operations

---

## 3. Queue

Implemented a `Queue` data structure with:

* enqueue
* dequeue

**Why this matters**
Queues are essential for:

* BFS (Breadth First Search)
* Scheduling
* Producer–consumer problems

---

## 4. Linked List

### Singly Linked List

```python
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None
```

Operations include:

* insertion
* deletion
* traversal
* reverse (iterative & recursive)

### Reverse Linked List (Iterative)

```python
def reverse(head):
    prev = None
    curr = head
    while curr:
        nxt = curr.next
        curr.next = prev
        prev = curr
        curr = nxt
    return prev
```

### Circular & XOR Linked List

Shows advanced pointer concepts and memory optimization ideas.

**Why this matters**
Linked lists teach:

* Pointer manipulation
* Dynamic memory concepts
* Foundation for stacks, queues, LRU cache

---

## 5. Heap

### Min Heap Implementation

```python
class MinHeap:
    def __init__(self):
        self.heap = []

    def parent(self, i):
        return (i - 1) // 2
```

Includes:

* insert
* heapify
* array → heap conversion

**Why this matters**
Heaps power:

* Priority Queues
* Dijkstra’s Algorithm
* Scheduling systems

---

## 6. Binary Search Tree (BST)

### Node Structure

```python
class BSTNode:
    def __init__(self, val):
        self.val = val
        self.left = None
        self.right = None
```

### Insert (Recursive)

```python
def insert(root, val):
    if not root:
        return BSTNode(val)
    if val < root.val:
        root.left = insert(root.left, val)
    else:
        root.right = insert(root.right, val)
    return root
```

Includes:

* recursive insert
* recursive search
* delete operation
* ceil value logic

**Why this matters**
BSTs introduce:

* Ordered data
* Logarithmic search
* Tree-based recursion patterns

---

## 7. Tree (General)

Covers:

* Tree node structure
* Traversals (recursive)

**Why this matters**
Trees model:

* File systems
* DOM
* Organization hierarchies

---

## 8. Graph

### Graph Representation

```python
class Graph:
    def __init__(self):
        self.graph = {}

    def add_edge(self, u, v):
        self.graph.setdefault(u, []).append(v)
```

Traversal patterns demonstrate how nodes are visited.

**Why this matters**
Graphs are everywhere:

* Social networks
* Maps & routing
* Dependency resolution

---

## 9. Tower of Hanoi (TOH)

Classic recursive problem demonstrating:

* Problem decomposition
* Recursive call flow

**Why this matters**
TOH is not about disks — it’s about *thinking recursively*.

---

## 10. Algorithmic Problems

### Stock Span Problem

Uses stack to compute spans efficiently.

### Subsets Generation

Classic recursion + backtracking pattern.

### Sum of Digits

Simple recursion strengthening base case logic.

**Why this matters**
These problems teach **patterns**, not just solutions.

---

## How to Use This Notebook

* Read code top-to-bottom
* Dry run with pen & paper
* Modify inputs and re-run
* Add print statements to trace execution

---

## Learning Philosophy

> Don’t memorize solutions.
> Understand *why* the data structure exists.

This notebook is meant to be:

* Interview prep
* Concept reinforcement
* A personal DSA reference

---

## Next Improvements (Optional)

* Add time & space complexity notes
* Convert problems into LeetCode-style format
* Add diagrams for trees & heaps

---
