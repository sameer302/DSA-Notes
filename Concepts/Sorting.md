# Sorting Concepts

## Stability
- A sorting algorithm is stable if it preserves the relative order of equal elements.
- For example, Original array (value, id): [(5,A), (3,B), (5,C), (2,D)]. After sorting by value, Stable sort: [(2,D), (3,B), (5,A), (5,C)], The two 5s remain in same order (A before C) and Unstable sort: [(2,D), (3,B), (5,C), (5,D)], The order of equal elements changed.
- Stability matters when sorting on multiple keys. For example, first sort employees by name and then by salary—you want employees with the same salary to remain alphabetically ordered.

## In-place and Out of place
- A sorting algorithm is in-place if it does not require any extra memory space during sorting or the space complexity of that algorithm is O(1).
- Out of place sorting algorithm will have space complexity of order O(n) where n is the number of elements to be sorted.

## Important points
- There is no single best sorting algorithm, it depends on availabe resources and application requirements (less memory with more time or less time with more memory) and also on the nature of the sorting elements (number of elements is less or more, if the array is nearly sorted then insertion sort is best)
- Hence most of the standard libraries of programming languages use adaptive sorting algorithms which analyzes the nature of workload and accordingly selects the best suitable algorithm.
- Best case with respect to sorting is when the array is already sorted and Worst case when it is perfectly reversed.
- Although both Selection Sort and Insertion Sort have a worst-case time complexity of (O(n^2)), Selection Sort performs only (n-1) swaps (about (3(n-1)) assignments), whereas Insertion Sort performs about (n(n-1)/2) shifts in the worst case. Therefore, if the cost of **writing to memory** is the main concern, Selection Sort is better because it does significantly fewer writes. However, in general-purpose computing, Insertion Sort is usually preferred because it is **adaptive** (runs in (O(n)) for nearly sorted arrays), has better cache performance due to sequential shifts, and performs much faster on small or partially sorted datasets despite doing more writes in the worst case.


# Sorting algorithms

## 1) Bubble Sort

- Repeatedly compare adjacent elements and swap if they are in the wrong order. Largest element "bubbles" to the end.
- Stable
- In-place
- Time Complexity:
  - Best - O(n) (if we add the condition that the inner loop breaks if no swap is done)
  - Average - O(n^2) 
  - Worst - O(n^2)
- More in the [link](https://www.geeksforgeeks.org/dsa/bubble-sort-algorithm/)

## 2) Selection Sort

- Selection Sort is a comparison-based sorting algorithm. It sorts by repeatedly selecting the smallest (or largest) element from the unsorted portion and swapping it with the first unsorted element.
- Unstable
- In-place
- Time Complexity:
  - Best - O(n^2) 
  - Average - O(n^2)
  - Worst - O(n^2)
- Requires less number of swaps or memory writes compared to bubble sort and many other sorting algorithms.
  - So it is suitable for small lists where the overhead of more complex algorithms isn't justified and memory writing is costly as it requires less memory writes compared to other standard sorting algorithms.
  - Heap sort is based on selection sort.
- More in the [link](https://www.geeksforgeeks.org/dsa/selection-sort-algorithm-2/)

## 3) Insertion Sort

-  It works by taking an element from the unsorted portion of a list and inserting it into its correct position relative to the already sorted elements.
-  Stable
-  In-place
-  Time Complexity:
  - Best: O(n) 
  - Average: O(n^2)
  - Worst: O(n^2)
- This algorithm is efficient for small lists and nearly sorted lists as it is adaptive. Also in worst case although the memory writes are more but the sequential shift operation is optimized.
  - Used as a subroutine in Bucket Sort
  - Also used in hybrid sorting algorithms like Introsort in C++ where if the subarray size becomes small, we switch to insertion sort.
- More in the [link](https://www.geeksforgeeks.org/dsa/insertion-sort-algorithm/) 
