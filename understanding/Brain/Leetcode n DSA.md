21-09-2025 23:52

Status : #study #cs #notes 

Tags : [[study]] [[job]] [[resources]] [[understanding/Tags/dsa|dsa]]

# Introduction

A comprehensive note of the resources needed for solving leetcode problems and approach in solving them.

My approach :
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

8 important patterns to solve leetcode problems can be split into two categories based on the type of data structure they work with :

- **Linear structures:** arrays, linked lists, strings
- **Nonlinear structures:** trees, graphs

## Linear Data Structure Patterns

1. **Two Pointers**
    - Reduces time complexity to linear time O(n).
    - Two methods:
        - _Same direction:_ scan data in a single pass (e.g., fast and slow pointers to detect cycles or find middle elements).
        - _Opposite directions:_ find pairs (e.g., sum of two numbers in a sorted array).
    - Notes : 
    - Problems : 
	    - [ ] [Leetcode - 167 : Two Sum II]()
	    - [ ] [Leetcode - 125 : Valid Palindrome]()
	    - [ ] [Leetcode - 283 : More Zeroes]()
	    - [ ] [Leetcode - 344 : Reverse String]()
	    - [ ] [Leetcode - 15 : 3Sum]()
	- Template :
```python : wrap
		class TwoPointers:
		    @staticmethod
		    def find_pair(nums, target):
		        left, right = 0, len(nums) - 1
		        while left < right:
		            current = nums[left] + nums[right]
		            if current == target:
		                return [left, right]
		            elif current < target:
		                left += 1
		            else:
		                right -= 1
		        return None
```

2. **Sliding Window**
    - Refines two pointers to manage a window of elements dynamically.
    - Expands or contracts the window to meet specific conditions (e.g., longest substring without repeating characters).
    - Often combined with hashmaps.
    - Notes : 
	    - Linear Data structures are used :
		    - Array
		    - Strings
		    - Linked List
		- longest or shortest substring/subarray that satisfies a certain condition
	- Problems : 
		- [ ] [Leetcode - 3 : Longest Substring Without Repeating Characters]()
		- [ ] [Leetcode - 76 : Minimum Window Substring]()
		- [ ] [Leetcode - 567 : Permutation in a String]()
		- [ ] [Leetcode - 438 : Find all Anagrams in a String]()
		- [ ] [Leetcode - 209 : Minimum Size Subarray Sum]()
3. **Binary Search**
    - Efficiently finds target in logarithmic time O(log⁡n).
    - Extends to lists with monotonic conditions, not just sorted numbers.
    - Example: finding the minimum in a rotated sorted array.
    - Notes :
    - Problems :
	    - [ ] [Leetcode - 704 : Binary Search]()
	    - [ ] [Leetcode - 35 : Search Insert Position]()
	    - [ ] [Leetcode - 153 : Find minimum in Rotated Sorted Array]()
	    - [ ] [Leetcode - 33 : - 33. Search in Rotated Sorted Array]()
	    - [ ] [Leetcode - 162 : - 162. Find Peak Element]()

## Nonlinear Data Structure Patterns

4. **Breadth-First Search (BFS)**
    - Explores nodes level by level.
    - Uses a queue to keep track of visited nodes (ideal for level order traversal).
    - Notes : 
	    - Starts at root.
	    - It explores all it's neighbors first.
	    - explores nodes level by level
	    - Best for shortest Path
	- Problems : 
		- [ ] [Leetcode - 102 : Binary Tree Level Order Traversal]()
		- [ ] [Leetcode - 200 : Number of Islands]()
		- [ ] [Leetcode - 886 : Possible Bipartition]()
		- [ ] [Leetcode - 1091 : Shortest Path in Binary Matrix]()
		- [ ] [Leetcode - 994 : Rotting Oranges]()
5. **Depth-First Search (DFS)**
    - Dives deep into one path before exploring others.
    - Often uses recursion and is memory efficient for exploring all paths.
    - Example: counting islands in a grid.
    - Notes : 
	    - Uses stack to explore nodes
	    - call stack -> Recursion
	    - Best for where we need to search all possible paths
	- Problems :
		- [ ] [Leetcode - 104 : Maximum Depth of Binary Tree]()
		- [ ] [Leetcode - 200 : Number of Islands]()
		- [ ] [Leetcode - 695 : Max Area of Island]()
		- [ ] [Leetcode - 78 : Subsets]()
		- [ ] [Leetcode - 131 : Palindrome Partitioning]()
6. **Backtracking**
    - Extension of DFS, explores all possible solutions.
    - Builds the solution dynamically by making decisions and backtracking on invalid paths.
    - Example: letter combinations of a phone number.
    - Notes :
    - Problems : 
	    - [ ] [Leetcode - 46 : Permutations]()
	    - [ ] [Leetcode - 39 : Combination Sum]()
	    - [ ] [Leetcode - 78. Subsets]()
	    - [ ] [Leetcode - 51 : N-Queens]()
	    - [ ] [Leetcode - 17. Letter Combinations of a Phone Number]()
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


