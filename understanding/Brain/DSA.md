21-09-2025 23:52

Status : #study #cs #notes 

Tags : [[study]] [[job]] [[resources]] [[understanding/Tags/dsa|dsa]]

# DSA

Here are the resources I'm gonna use to Prepare for DSA and Leetcode problems

Basic approach :
1. Getting Basic idea about the most common patterns
2. Use this common patterns as black box modules to see how they are applied
3. Explore the common patterns in depth
4. Implement each pattern 
5. Write short-essays or blogs on each pattern
6. Create the Black Box module 
7. Publish a blog exploring the black box module
8. Use this module to solve leetcode problems
9. Explore other Patterns
10. Repeat 1- 5
11. Add these new patterns into the existing module

## Notes
---
# Introduction

8 important patterns for coding interviews split into two categories:

- **Linear structures:** arrays, linked lists, strings
- **Nonlinear structures:** trees, graphs

Focus is on pre-built code templates for these patterns.

## Linear Data Structure Patterns

1. **Two Pointers**
    
    - Reduces time complexity to linear time O(n).
    - Two methods:
        - _Same direction:_ scan data in a single pass (e.g., fast and slow pointers to detect cycles or find middle elements).
        - _Opposite directions:_ find pairs (e.g., sum of two numbers in a sorted array).
2. **Sliding Window**
    - Refines two pointers to manage a window of elements dynamically.
    - Expands or contracts the window to meet specific conditions (e.g., longest substring without repeating characters).
    - Often combined with hashmaps.
3. **Binary Search**
    - Efficiently finds target in logarithmic time O(log⁡n).
    - Extends to lists with monotonic conditions, not just sorted numbers.
    - Example: finding the minimum in a rotated sorted array.

## Nonlinear Data Structure Patterns

4. **Breadth-First Search (BFS)**
    - Explores nodes level by level.
    - Uses a queue to keep track of visited nodes (ideal for level order traversal).
5. **Depth-First Search (DFS)**
    - Dives deep into one path before exploring others.
    - Often uses recursion and is memory efficient for exploring all paths.
    - Example: counting islands in a grid.
6. **Backtracking**
    - Extension of DFS, explores all possible solutions.
    - Builds the solution dynamically by making decisions and backtracking on invalid paths.
    - Example: letter combinations of a phone number.

## Heaps (Priority Queue)

7. **Heaps**
    - Used for questions related to top K, K smallest/largest.
    - **Min Heap:** smallest value at the root.
    - **Max Heap:** largest value at the root.
    - Max Heap is used to find K smallest values, and vice versa for K largest.

## Dynamic Programming (DP)

8. **Dynamic Programming**
    - Optimizes solutions by breaking problems into overlapping subproblems.
    - Two approaches:
        - _Top-down:_ recursive with memoization to store results.
        - _Bottom-up:_ solves smaller subproblems iteratively using a table.

---

# References

- [x]  [8 Patterns Basic Overview](https://youtu.be/xo7XrRVxH8Y) 
- [x] [Leetcode Patterns & Templates](https://youtu.be/RYT08CaYq6A)
- [ ] [DSA Paterns for Leetcode Interview](https://youtu.be/Z_c4byLrNBU)
- [ ] [10 Common Coding Interview Questions](https://youtu.be/Peq4GCPNC5c)
- [ ] [Neetcode 150 Course](https://youtu.be/T0u5nwSA0w0)
- [ ] [Dynamic Programming](https://youtu.be/oBt53YbR9Kk)
- [ ] [Beyond Cracking the Coding Interview](https://drive.google.com/drive/folders/1AdUu4jh6DGwmCxfgnDQEMWWyo6_whPHJ)
- [ ] [BCCI interview](https://start.interviewing.io/beyond-ctci/all-problems/technical-topics)
- [ ] [[Cracking the Coding Interview.pdf]]


