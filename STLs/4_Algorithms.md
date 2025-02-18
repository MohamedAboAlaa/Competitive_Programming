# Algorithms in C++ Standard Template Library (STL)

## Introduction
Algorithms are an essential part of the C++ Standard Template Library (STL). They provide efficient ways to manipulate and process data stored in containers. STL algorithms operate on iterators, making them versatile and applicable to various container types.

STL algorithms can be broadly classified into different categories based on their functionality.

---

## 1. Non-Modifying Algorithms
These algorithms perform operations on containers without altering their elements.

### **Searching Algorithms**
- `std::find(it1, it2, value)`: Finds the first occurrence of `value` in the given range.
- `std::count(it1, it2, value)`: Counts occurrences of `value` in the given range.
- `std::equal(it1, it2, it3)`: Checks if two ranges are equal.
- `std::search(it1, it2, it3, it4)`: Searches for a subsequence in a range.

### **Comparing Algorithms**
- `std::min(a, b)`: Returns the smaller of `a` and `b`.
- `std::max(a, b)`: Returns the larger of `a` and `b`.
- `std::min_element(it1, it2)`: Finds the smallest element in a range.
- `std::max_element(it1, it2)`: Finds the largest element in a range.
- `std::lexicographical_compare(it1, it2, it3, it4)`: Compares two sequences lexicographically.

---

## 2. Modifying Algorithms
These algorithms modify the contents of containers.

### **Copying and Moving Algorithms**
- `std::copy(it1, it2, dest_it)`: Copies elements from one range to another.
- `std::move(it1, it2, dest_it)`: Moves elements from one range to another.
- `std::swap(a, b)`: Swaps the values of `a` and `b`.
- `std::swap_ranges(it1, it2, it3)`: Swaps elements between two ranges.

### **Filling and Replacing Algorithms**
- `std::fill(it1, it2, value)`: Fills a range with `value`.
- `std::generate(it1, it2, func)`: Fills a range using a function.
- `std::replace(it1, it2, old_value, new_value)`: Replaces occurrences of `old_value` with `new_value`.
- `std::replace_if(it1, it2, condition, new_value)`: Replaces elements that satisfy a condition with `new_value`.

### **Removing Algorithms**
- `std::remove(it1, it2, value)`: Removes elements equal to `value`.
- `std::remove_if(it1, it2, condition)`: Removes elements satisfying a condition.
- `std::unique(it1, it2)`: Removes consecutive duplicate elements.

---

## 3. Sorting and Ordering Algorithms
These algorithms arrange elements in a specific order.

- `std::sort(it1, it2)`: Sorts elements in ascending order.
- `std::stable_sort(it1, it2)`: Sorts elements while preserving the order of equal elements.
- `std::partial_sort(it1, mid, it2)`: Partially sorts elements such that the smallest values appear first.
- `std::nth_element(it1, nth, it2)`: Partially sorts elements so that the `nth` element is at its correct position.
- `std::partition(it1, it2, condition)`: Reorders elements so that elements satisfying `condition` come first.

---

## 4. Numeric Algorithms
These algorithms perform mathematical operations on containers.

- `std::accumulate(it1, it2, init)`: Computes the sum of a range.
- `std::inner_product(it1, it2, it3, init)`: Computes the inner product of two ranges.
- `std::adjacent_difference(it1, it2, dest_it)`: Computes the difference between adjacent elements.
- `std::partial_sum(it1, it2, dest_it)`: Computes the partial sum of elements in a range.

---

## 5. Heap Operations
These algorithms operate on heap structures.

- `std::make_heap(it1, it2)`: Converts a range into a heap.
- `std::push_heap(it1, it2)`: Adds an element to a heap.
- `std::pop_heap(it1, it2)`: Removes the largest element from a heap.
- `std::sort_heap(it1, it2)`: Sorts a heap into a sorted sequence.

---

## 6. Permutation and Combination Algorithms
These algorithms help in generating different permutations and combinations.

- `std::next_permutation(it1, it2)`: Generates the next lexicographic permutation.
- `std::prev_permutation(it1, it2)`: Generates the previous lexicographic permutation.

---

## Choosing the Right Algorithm
Choosing the right STL algorithm depends on the problem requirements:

| Use Case | Recommended Algorithm |
|----------|---------------------|
| Searching for an element | `std::find`, `std::binary_search` |
| Sorting a container | `std::sort`, `std::stable_sort` |
| Counting elements | `std::count`, `std::accumulate` |
| Removing duplicates | `std::unique`, `std::remove` |
| Performing mathematical operations | `std::accumulate`, `std::inner_product` |

---
