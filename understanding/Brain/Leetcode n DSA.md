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
	    - [ ] [Leetcode - 167 : Two Sum II](https://leetcode.com/problems/two-sum-ii-input-array-is-sorted/description/)
	    - [ ] [Leetcode - 125 : Valid Palindrome](https://leetcode.com/problems/valid-palindrome/description/)
	    - [ ] [Leetcode - 283 : More Zeroes](https://leetcode.com/problems/move-zeroes/description/)
	    - [ ] [Leetcode - 344 : Reverse String](https://leetcode.com/problems/reverse-string/description/)
	    - [ ] [Leetcode - 15 : 3Sum](https://leetcode.com/problems/3sum/description/)
	- Template :
````python
		class TwoPointers:
		    @staticmethod
		    def run(nums, callback, left=0, right=None):
		        """Iteratively applies callback at each (left, right) until                    left < right. callback receives (nums, left, right) and                     must return how to move pointers.
		        """
                if right is None: right = len(nums) - 1
			        while left < right:
			            left, right = callback(nums, left, right)

````
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
		- [ ] [Leetcode - 3 : Longest Substring Without Repeating Characters](https://leetcode.com/problems/longest-substring-without-repeating-characters/description/)
		- [ ] [Leetcode - 76 : Minimum Window Substring](https://leetcode.com/problems/minimum-window-substring/description/)
		- [ ] [Leetcode - 567 : Permutation in a String](https://leetcode.com/problems/permutation-in-string/description/)
		- [ ] [Leetcode - 438 : Find all Anagrams in a String](https://leetcode.com/problems/find-all-anagrams-in-a-string/description/)
		- [ ] [Leetcode - 209 : Minimum Size Subarray Sum](https://leetcode.com/problems/minimum-size-subarray-sum/description/)
	- Template :
```Python 
	class SlidingWindow:
    @staticmethod
    def run(nums, window_size, process_window):
        """Moves a window of window_size, calls process_window on each                 window.
        """
        for i in range(len(nums) - window_size + 1):
            process_window(nums[i:i+window_size], i, i + window_size - 1)

	```
3. **Binary Search**
    - Efficiently finds target in logarithmic time O(log⁡n).
    - Extends to lists with monotonic conditions, not just sorted numbers.
    - Example: finding the minimum in a rotated sorted array.
    - Notes :
    - Problems :
	    - [ ] [Leetcode - 704 : Binary Search](https://leetcode.com/problems/binary-search/description/)
	    - [ ] [Leetcode - 35 : Search Insert Position](https://leetcode.com/problems/search-insert-position/description/)
	    - [ ] [Leetcode - 153 : Find minimum in Rotated Sorted Array](https://leetcode.com/problems/find-minimum-in-rotated-sorted-array/description/)
	    - [ ] [Leetcode - 33 : Search in Rotated Sorted Array](https://leetcode.com/problems/search-in-rotated-sorted-array/description/)
	    - [ ] [Leetcode - 162 : Find Peak Element](https://leetcode.com/problems/find-peak-element/description/)
	- Template :
```Python
	class BinarySearch:
	    @staticmethod
	    def run(lo, hi, condition):
	        """Finds the first 'hi' satisfying condition.
	        'condition' is a function returning True/False."""
	        while lo < hi:
	            mid = lo + (hi - lo)//2
	            if condition(mid):
	                hi = mid
	            else:
	                lo = mid + 1
	        return lo

```

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
		- [ ] [Leetcode - 102 : Binary Tree Level Order Traversal](https://leetcode.com/problems/binary-tree-level-order-traversal/description/)
		- [ ] [Leetcode - 200 : Number of Islands](https://leetcode.com/problems/number-of-islands/description/)
		- [ ] [Leetcode - 886 : Possible Bipartition](https://leetcode.com/problems/possible-bipartition/description/)
		- [ ] [Leetcode - 1091 : Shortest Path in Binary Matrix](https://leetcode.com/problems/shortest-path-in-binary-matrix/description/)
		- [ ] [Leetcode - 994 : Rotting Oranges](https://leetcode.com/problems/rotting-oranges/description/)
	- Templates : 
```Python
	from collections import deque
	
	class BFS:
	    @staticmethod
	    def run(start_nodes, get_neighbors, process_node=None):
	        """Generic BFS traversal from start_nodes."""
	        queue = deque(start_nodes)
	        visited = set(start_nodes)
	        while queue:
	            node = queue.popleft()
	            if process_node: process_node(node)
	            for neighbor in get_neighbors(node):
	                if neighbor not in visited:
	                    visited.add(neighbor)
	                    queue.append(neighbor)

```
4. **Depth-First Search (DFS)**
    - Dives deep into one path before exploring others.
    - Often uses recursion and is memory efficient for exploring all paths.
    - Example: counting islands in a grid.
    - Notes : 
	    - Uses stack to explore nodes
	    - call stack -> Recursion
	    - Best for where we need to search all possible paths
	- Problems :
		- [ ] [Leetcode - 104 : Maximum Depth of Binary Tree](https://leetcode.com/problems/maximum-depth-of-binary-tree/description/)
		- [ ] [Leetcode - 200 : Number of Islands](https://leetcode.com/problems/number-of-islands/description/)
		- [ ] [Leetcode - 695 : Max Area of Island](https://leetcode.com/problems/max-area-of-island/description/)
		- [ ] [Leetcode - 78 : Subsets](https://leetcode.com/problems/subsets/description/)
		- [ ] [Leetcode - 131 : Palindrome Partitioning](https://leetcode.com/problems/palindrome-partitioning/description/)
	- Template :
```Python 
	class DFS:
	    @staticmethod
	    def run(node, get_neighbors, process_node=None, visited=None):
	        """Generic DFS traversal starting at node."""
	        if visited is None: visited = set()
	        if node in visited: return
	        visited.add(node)
	        if process_node: process_node(node)
	        for neighbor in get_neighbors(node):
	            DFS.run(neighbor, get_neighbors, process_node, visited)

```
4. **Backtracking**
    - Extension of DFS, explores all possible solutions.
    - Builds the solution dynamically by making decisions and backtracking on invalid paths.
    - Example: letter combinations of a phone number.
    - Notes :
    - Problems : 
	    - [ ] [Leetcode - 46 : Permutations](https://leetcode.com/problems/permutations/description/)
	    - [ ] [Leetcode - 39 : Combination Sum](https://leetcode.com/problems/combination-sum/description/)
	    - [ ] [Leetcode - 78. Subsets](https://leetcode.com/problems/subsets/description/)
	    - [ ] [Leetcode - 51 : N-Queens](https://leetcode.com/problems/n-queens/description/)
	    - [ ] [Leetcode - 17 : Letter Combinations of a Phone Number](https://leetcode.com/problems/letter-combinations-of-a-phone-number/description/)
	- Template :
```Python
	class Backtracking:
	    @staticmethod
	    def run(path, options, goal_condition, choose, unchoose, result):
	        """Recursive backtracking, user defines choose/unchoose,                       goal_condition.
	        """
	        if goal_condition(path):
	            result.append(list(path))
	            return
	        for option in options:
	            choose(option, path)
	            Backtracking.run(path, options, goal_condition, 
						            choose, unchoose, result)
	            unchoose(option, path)

```
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


