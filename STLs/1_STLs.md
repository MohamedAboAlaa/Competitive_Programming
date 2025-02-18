# Standard Template Library (STL) in C++

## What is STL?
STL (Standard Template Library) is a collection of pre-defined classes and functions in C++ that help in handling data structures and algorithms efficiently. It provides reusable and efficient code to perform common operations.

## Components of STL
STL has three main components:

1. **Containers** - Used to store data.
2. **Algorithms** - Functions that perform operations on containers.
3. **Iterators** - Objects used to traverse containers.

---

## 1. Containers
Containers are data structures that store objects. They are divided into three types:

### a) Sequence Containers
These store data in a linear order.
- **Vector** - A dynamic array that can grow and shrink in size.
- **List** - A doubly linked list that allows efficient insertion and deletion.
- **Deque** - A double-ended queue that allows fast insertion and deletion from both ends.

### b) Associative Containers
These store data in key-value pairs and provide fast retrieval.
- **Set** - Stores unique elements in a sorted manner.
- **Multiset** - Similar to a set, but allows duplicate elements.
- **Map** - Stores key-value pairs in a sorted manner, where each key is unique.
- **Multimap** - Similar to a map, but allows duplicate keys.

### c) Unordered Containers
These store data in an unordered manner, providing faster lookup times using hash tables.
- **Unordered Set** - Similar to a set but does not store elements in sorted order.
- **Unordered Multiset** - Similar to a multiset but unordered.
- **Unordered Map** - Similar to a map but unordered.
- **Unordered Multimap** - Similar to a multimap but unordered.

---

## 2. Algorithms
STL provides a variety of built-in algorithms that can be used for different operations. Some commonly used algorithms include:

- **Sorting** - `sort()`, `stable_sort()`
- **Searching** - `binary_search()`, `find()`
- **Modifying** - `reverse()`, `replace()`, `swap()`
- **Numeric** - `accumulate()`, `partial_sum()`
- **Heap operations** - `make_heap()`, `push_heap()`, `pop_heap()`, `sort_heap()`

These algorithms work efficiently with STL containers and help in writing optimized code.

---

## 3. Iterators
Iterators are objects that help in traversing through containers. They provide a way to access container elements without exposing the underlying data structure.

### Types of Iterators
- **Input Iterators** - Used for reading values from containers.
- **Output Iterators** - Used for writing values to containers.
- **Forward Iterators** - Can move forward in a sequence.
- **Bidirectional Iterators** - Can move both forward and backward.
- **Random Access Iterators** - Can move to any position in constant time.

Iterators make it easier to traverse and manipulate data in a container efficiently.

---
