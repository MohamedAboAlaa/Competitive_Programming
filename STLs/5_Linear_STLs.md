# Linear Data Structures in C++ STL

## Introduction
Linear Data Structures (DS) are data structures where elements are arranged sequentially, and each element is connected to its previous and next element. In C++, the Standard Template Library (STL) provides multiple linear data structures that simplify development and improve efficiency.

STL offers the following linear data structures:
- **Vector**
- **Deque**
- **List**
- **Stack**
- **Queue**

Each of these structures has its own advantages and use cases.

---

## 1. Vector
### **Overview**
A `vector` is a dynamic array that can grow and shrink in size. It provides fast random access and is highly efficient for element retrieval.

### **Key Features**
- **Dynamic resizing** (automatically grows as needed)
- **Random access in O(1) time**
- **Efficient insertion and deletion at the end**
- **More memory consumption due to dynamic growth**

### **Common Operations and Complexities**
- **Accessing Elements**: `v[i]`, `v.at(i)` → **O(1)**
- **Adding Elements**: `push_back(value)` → **O(1) amortized**, `insert(position, value)` → **O(n)**
- **Removing Elements**: `pop_back()` → **O(1)**, `erase(position)` → **O(n)**
- **Size Management**: `size()` → **O(1)**, `capacity()` → **O(1)**, `resize(new_size)` → **O(n)**
- **Sorting**: `sort(v.begin(), v.end())` → **O(n log n)**

### **C++ Code Example**
```cpp
#include <iostream>
#include <vector>
#include <algorithm>
using namespace std;

int main() {
    vector<int> v = {10, 20, 30};
    v.push_back(40); // Insert at end
    v.insert(v.begin() + 1, 15); // Insert at position 1
    v.pop_back(); // Remove last element
    sort(v.begin(), v.end()); // Sorting

    for (int x : v) {
        cout << x << " ";
    }
    return 0;
}
```
**Expected Output:**
```cpp
10 15 20 30 
```

### **Use Cases**
- When frequent random access is needed
- Storing elements that change dynamically

---

## 2. Deque (Double-Ended Queue)
### **Overview**
A `deque` (double-ended queue) allows insertion and deletion from both the front and the back efficiently.

### **Key Features**
- **Efficient insertions/deletions at both ends**
- **Random access like vectors**
- **More memory overhead than vectors**

### **Common Operations and Complexities**
- **Accessing Elements**: `d[i]`, `d.at(i)` → **O(1)**
- **Adding Elements**: `push_front(value)`, `push_back(value)` → **O(1)**
- **Removing Elements**: `pop_front()`, `pop_back()` → **O(1)**
- **Size Management**: `size()` → **O(1)**, `resize(new_size)` → **O(n)**
- **Sorting**: `sort(d.begin(), d.end())` → **O(n log n)**

### **C++ Code Example**
```cpp
#include <iostream>
#include <deque>
#include <algorithm>
using namespace std;

int main() {
    deque<int> d = {10, 20, 30};
    d.push_front(5); // Insert at front
    d.push_back(40); // Insert at back
    d.pop_front(); // Remove from front
    d.pop_back(); // Remove from back
    sort(d.begin(), d.end());

    for (int x : d) {
        cout << x << " ";
    }
    return 0;
}
```
**Expected Output:**
```cpp
10 20 30 
```

---

## 3. List (Doubly Linked List)
### **C++ Code Example**
```cpp
#include <iostream>
#include <list>
using namespace std;

int main() {
    list<int> l = {10, 20, 30};
    l.push_front(5); // Insert at front
    l.push_back(40); // Insert at back
    l.pop_front(); // Remove from front
    l.pop_back(); // Remove from back

    for (int x : l) {
        cout << x << " ";
    }
    return 0;
}
```
**Expected Output:**
```cpp
10 20 30 
```

---

## 4. Stack
### **C++ Code Example**
```cpp
#include <iostream>
#include <stack>
using namespace std;

int main() {
    stack<int> s;
    s.push(10);
    s.push(20);
    s.push(30);
    cout << s.top() << endl; // Top element
    s.pop();
    cout << s.top() << endl;
    return 0;
}
```
**Expected Output:**
```cpp
30
20
```

---

## 5. Queue
### **C++ Code Example**
```cpp
#include <iostream>
#include <queue>
using namespace std;

int main() {
    queue<int> q;
    q.push(10);
    q.push(20);
    q.push(30);
    cout << q.front() << endl; // Front element
    q.pop();
    cout << q.front() << endl;
    return 0;
}
```
**Expected Output:**
```cpp
10
20
```

---

## Choosing the Right Linear Data Structure
| Use Case | Recommended STL Data Structure |
|----------|-------------------------------|
| Fast random access | Vector |
| Frequent insertions/deletions at both ends | Deque |
| Insertions/deletions anywhere | List |
| LIFO operations | Stack |
| FIFO operations | Queue |

---
