
# Non-Linear Data Structures in C++ STL

Non-linear data structures are those in which elements are not stored sequentially, and the relationship between elements is hierarchical, or in some cases, there is no clear sequence. Common non-linear data structures include trees and graphs, but in C++ Standard Template Library (STL), several associative containers and priority queues also exhibit non-linear behavior.

### 1. **Set** (`std::set`)

A `set` is a container that stores unique elements, and it automatically sorts the elements in ascending order (by default). It uses a self-balancing binary search tree (typically a Red-Black Tree).

#### Key Operations:

- **Insert**: Inserts an element, maintaining sorted order.
- **Erase**: Removes an element.
- **Find**: Finds an element in the set.
- **Size**: Returns the number of elements in the set.
- **Empty**: Checks if the set is empty.

#### Time Complexity:
- **Insert**: O(log n)
- **Erase**: O(log n)
- **Find**: O(log n)
- **Size**: O(1)
- **Empty**: O(1)

#### Example Code:

```cpp
#include <iostream>
#include <set>

int main() {
    std::set<int> mySet;

    // Inserting elements
    mySet.insert(10);
    mySet.insert(20);
    mySet.insert(5);

    // Printing the elements
    std::cout << "Set elements: ";
    for (int element : mySet) {
        std::cout << element << " ";
    }
    std::cout << std::endl;

    // Finding an element
    if (mySet.find(10) != mySet.end()) {
        std::cout << "10 found in the set." << std::endl;
    }

    // Erasing an element
    mySet.erase(20);
    std::cout << "After erasing 20, set elements: ";
    for (int element : mySet) {
        std::cout << element << " ";
    }
    std::cout << std::endl;

    return 0;
}
```

#### Expected Output:

```
Set elements: 5 10 20 
10 found in the set.
After erasing 20, set elements: 5 10
```

### 2. **Multiset** (`std::multiset`)

A `multiset` is similar to a `set`, but it allows duplicate elements. It automatically keeps the elements sorted in ascending order.

#### Key Operations:

- **Insert**: Inserts an element, allowing duplicates.
- **Erase**: Removes an element.
- **Find**: Finds an element in the multiset.
- **Size**: Returns the number of elements in the multiset.
- **Empty**: Checks if the multiset is empty.

#### Time Complexity:
- **Insert**: O(log n)
- **Erase**: O(log n)
- **Find**: O(log n)
- **Size**: O(1)
- **Empty**: O(1)

#### Example Code:

```cpp
#include <iostream>
#include <set>

int main() {
    std::multiset<int> myMultiSet;

    // Inserting elements
    myMultiSet.insert(10);
    myMultiSet.insert(20);
    myMultiSet.insert(20);
    myMultiSet.insert(5);

    // Printing the elements
    std::cout << "Multiset elements: ";
    for (int element : myMultiSet) {
        std::cout << element << " ";
    }
    std::cout << std::endl;

    // Erasing an element
    myMultiSet.erase(20);
    std::cout << "After erasing 20, multiset elements: ";
    for (int element : myMultiSet) {
        std::cout << element << " ";
    }
    std::cout << std::endl;

    return 0;
}
```

#### Expected Output:

```
Multiset elements: 5 10 20 20 
After erasing 20, multiset elements: 5 10 20
```

### 3. **Map** (`std::map`)

A `map` is a collection of key-value pairs, where keys are unique and are stored in sorted order (by default, in ascending order). The map uses a self-balancing binary search tree.

#### Key Operations:

- **Insert**: Inserts a key-value pair.
- **Erase**: Removes a key-value pair by key.
- **Find**: Finds an element by key.
- **At**: Returns the value corresponding to a key.
- **Size**: Returns the number of elements in the map.

#### Time Complexity:
- **Insert**: O(log n)
- **Erase**: O(log n)
- **Find**: O(log n)
- **At**: O(log n)
- **Size**: O(1)

#### Example Code:

```cpp
#include <iostream>
#include <map>

int main() {
    std::map<int, std::string> myMap;

    // Inserting key-value pairs
    myMap[1] = "one";
    myMap[2] = "two";
    myMap[3] = "three";

    // Printing the map
    std::cout << "Map elements:
";
    for (const auto& pair : myMap) {
        std::cout << pair.first << ": " << pair.second << std::endl;
    }

    // Finding an element
    if (myMap.find(2) != myMap.end()) {
        std::cout << "Key 2 found with value: " << myMap[2] << std::endl;
    }

    return 0;
}
```

#### Expected Output:

```
Map elements:
1: one
2: two
3: three
Key 2 found with value: two
```

### 4. **Multimap** (`std::multimap`)

A `multimap` allows multiple values for a single key, so it is similar to a `map`, but unlike a `map`, it allows duplicate keys.

#### Key Operations:

- **Insert**: Inserts a key-value pair (duplicates allowed).
- **Erase**: Removes a key-value pair by key.
- **Find**: Finds an element by key.
- **Size**: Returns the number of elements in the multimap.

#### Time Complexity:
- **Insert**: O(log n)
- **Erase**: O(log n)
- **Find**: O(log n)
- **Size**: O(1)

#### Example Code:

```cpp
#include <iostream>
#include <map>

int main() {
    std::multimap<int, std::string> myMultiMap;

    // Inserting key-value pairs
    myMultiMap.insert({1, "one"});
    myMultiMap.insert({1, "uno"});
    myMultiMap.insert({2, "two"});

    // Printing the multimap
    std::cout << "Multimap elements:
";
    for (const auto& pair : myMultiMap) {
        std::cout << pair.first << ": " << pair.second << std::endl;
    }

    return 0;
}
```

#### Expected Output:

```
Multimap elements:
1: one
1: uno
2: two
```

### 5. **Priority Queue** (`std::priority_queue`)

A `priority_queue` is a container adapter that provides constant time access to the largest (or smallest) element. By default, it behaves as a max-heap.

#### Key Operations:

- **Push**: Adds an element to the queue.
- **Pop**: Removes the largest element.
- **Top**: Returns the largest element.
- **Size**: Returns the number of elements in the priority queue.

#### Time Complexity:
- **Push**: O(log n)
- **Pop**: O(log n)
- **Top**: O(1)
- **Size**: O(1)

#### Example Code:

```cpp
#include <iostream>
#include <queue>

int main() {
    std::priority_queue<int> pq;

    // Inserting elements
    pq.push(10);
    pq.push(20);
    pq.push(5);

    // Printing the top element
    std::cout << "Top element: " << pq.top() << std::endl;

    // Popping the top element
    pq.pop();
    std::cout << "After popping, top element: " << pq.top() << std::endl;

    return 0;
}
```

#### Expected Output:

```
Top element: 20
After popping, top element: 10
```

### 6. **Unordered Set** (`std::unordered_set`)

An `unordered_set` is an associative container that stores unique elements, but unlike `set`, the elements are not sorted. It uses hash tables to store the elements.

#### Key Operations:

- **Insert**: Inserts an element.
- **Erase**: Removes an element.
- **Find**: Finds an element.
- **Size**: Returns the number of elements in the unordered set.

#### Time Complexity:
- **Insert**: O(1) on average
- **Erase**: O(1) on average
- **Find**: O(1) on average
- **Size**: O(1)

#### Example Code:

```cpp
#include <iostream>
#include <unordered_set>

int main() {
    std::unordered_set<int> myUnorderedSet;

    // Inserting elements
    myUnorderedSet.insert(10);
    myUnorderedSet.insert(20);
    myUnorderedSet.insert(5);

    // Printing the unordered set
    std::cout << "Unordered set elements: ";
    for (int element : myUnorderedSet) {
        std::cout << element << " ";
    }
    std::cout << std::endl;

    return 0;
}
```

#### Expected Output:

```
Unordered set elements: 5 10 20 
```

### 7. **Unordered Map** (`std::unordered_map`)

An `unordered_map` is a container that stores key-value pairs with keys being unique, but the elements are not stored in any sorted order. It uses a hash table for fast lookups.

#### Key Operations:

- **Insert**: Inserts a key-value pair.
- **Erase**: Removes a key-value pair.
- **Find**: Finds an element by key.
- **At**: Returns the value for a key.
- **Size**: Returns the number of elements.

#### Time Complexity:
- **Insert**: O(1) on average
- **Erase**: O(1) on average
- **Find**: O(1) on average
- **At**: O(1)
- **Size**: O(1)

#### Example Code:

```cpp
#include <iostream>
#include <unordered_map>

int main() {
    std::unordered_map<int, std::string> myUnorderedMap;

    // Inserting key-value pairs
    myUnorderedMap[1] = "one";
    myUnorderedMap[2] = "two";
    myUnorderedMap[3] = "three";

    // Printing the unordered map
    std::cout << "Unordered map elements:
";
    for (const auto& pair : myUnorderedMap) {
        std::cout << pair.first << ": " << pair.second << std::endl;
    }

    return 0;
}
```

#### Expected Output:

```
Unordered map elements:
1: one
2: two
3: three
```

### 8. **Unordered Multiset** (`std::unordered_multiset`)

An `unordered_multiset` allows duplicate elements, like `multiset`, but the elements are not stored in any particular order.

#### Key Operations:

- **Insert**: Inserts an element (duplicates allowed).
- **Erase**: Removes an element.
- **Find**: Finds an element.
- **Size**: Returns the number of elements.

#### Time Complexity:
- **Insert**: O(1) on average
- **Erase**: O(1) on average
- **Find**: O(1) on average
- **Size**: O(1)

#### Example Code:

```cpp
#include <iostream>
#include <unordered_set>

int main() {
    std::unordered_multiset<int> myUnorderedMultiSet;

    // Inserting elements
    myUnorderedMultiSet.insert(10);
    myUnorderedMultiSet.insert(20);
    myUnorderedMultiSet.insert(10);

    // Printing the unordered multiset
    std::cout << "Unordered multiset elements: ";
    for (int element : myUnorderedMultiSet) {
        std::cout << element << " ";
    }
    std::cout << std::endl;

    return 0;
}
```

#### Expected Output:

```
Unordered multiset elements: 10 20 10 
```

### 9. **Unordered Multimap** (`std::unordered_multimap`)

An `unordered_multimap` allows multiple key-value pairs with duplicate keys. Like `unordered_map`, it stores elements using a hash table.

#### Key Operations:

- **Insert**: Inserts a key-value pair (duplicates allowed).
- **Erase**: Removes a key-value pair.
- **Find**: Finds an element by key.

#### Time Complexity:
- **Insert**: O(1) on average
- **Erase**: O(1) on average
- **Find**: O(1) on average
- **Size**: O(1)

#### Example Code:

```cpp
#include <iostream>
#include <unordered_map>

int main() {
    std::unordered_multimap<int, std::string> myUnorderedMultiMap;

    // Inserting key-value pairs
    myUnorderedMultiMap.insert({1, "one"});
    myUnorderedMultiMap.insert({1, "uno"});
    myUnorderedMultiMap.insert({2, "two"});

    // Printing the unordered multimap
    std::cout << "Unordered multimap elements:
";
    for (const auto& pair : myUnorderedMultiMap) {
        std::cout << pair.first << ": " << pair.second << std::endl;
    }

    return 0;
}
```

#### Expected Output:

```
Unordered multimap elements:
1: one
1: uno
2: two
```

---
