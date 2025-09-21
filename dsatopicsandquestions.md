# ![DSA](https://img.shields.io/badge/DSA-Java-blue?style=for-the-badge) ![Interview](https://img.shields.io/badge/Interview-Preparation-brightgreen?style=for-the-badge) ![ProductionReady](https://img.shields.io/badge/Production-Ready-orange?style=for-the-badge)

# 📘 DSA Interview Preparation in Java

---

## 📑 Table of Contents
- [Basics](#basics)
- [Arrays](#arrays)
- [Strings](#strings)
- [Linked Lists](#linked-lists)
- [Stacks](#stacks)
- [Queues](#queues)
- [Hashing](#hashing)
- [Trees (Binary, BST, Trie)](#trees)
- [Graphs](#graphs)
- [Heaps](#heaps)
- [Recursion & Backtracking](#recursion--backtracking)
- [Dynamic Programming](#dynamic-programming)
- [Sorting & Searching](#sorting--searching)
- [Greedy Algorithms](#greedy-algorithms)
- [Sliding Window & Two Pointers](#sliding-window--two-pointers)
- [Problem-Solving Patterns](#problem-solving-patterns)
- [⚡ Production-Level Scenarios](#-production-level-scenarios)
- [🔥 Top 10 Frequently Asked DSA Questions](#-top-10-frequently-asked-dsa-questions)
- [✅ Best Practices](#-best-practices)
- [🛠 Cheat Sheet](#-cheat-sheet)

---

## Basics
<details>
<summary>Click to expand</summary>

### Easy
1. ⚡ **What is the difference between Array and ArrayList in Java?**  
   - Array: fixed size, can store primitives.  
   - ArrayList: dynamic size, stores objects only.  

2. **Explain time complexity of HashMap operations.**  
   - Average: O(1), Worst: O(n) (hash collisions).  

3. **What is Big-O notation?**  
   - Mathematical representation of time/space complexity.

---

### Medium
4. **Explain difference between Stack and Queue.**  
   - Stack: LIFO, Queue: FIFO.  

5. **What is the difference between LinkedList and ArrayList in Java?**  
   - ArrayList: random access O(1).  
   - LinkedList: insertion/deletion O(1) at head/tail.  

6. **How does Java Garbage Collection work?**  
   - Automatically removes unreachable objects (generational collection).

---

### Hard
7. **Explain Thread-safety in collections.**  
   - Use `Collections.synchronizedList()` or `ConcurrentHashMap`.  

8. **Difference between primitive and wrapper classes?**  
   - Wrapper allows use in collections, has methods, can be null.  

9. **How HashCode & Equals work in Java collections?**  
   - HashMap/Set uses hashCode() to find bucket, equals() to resolve collisions.  

10. **Explain Immutability in Strings. Why is it important?**  
   - Security, caching, thread-safety.  

</details>

---

## Arrays
<details>
<summary>Click to expand</summary>

### Easy
1. Find maximum element in an array. → O(n).  
2. Find second largest element. → Track max & secondMax.  
3. Reverse an array. → Two-pointer swap.  

### Medium
4. Two Sum problem (pair with given sum). → HashMap O(n).  
5. Subarray with given sum. → Prefix sum or sliding window.  
6. Rotate array by k steps. → Reverse trick.  

### Hard
7. Maximum subarray sum (Kadane’s Algo). → O(n).  
8. Trapping Rain Water. → Two pointers.  
9. Merge intervals. → Sort + merge.  
10. Median of two sorted arrays. → Binary search O(log(min(n,m))).  

</details>

---

## Strings
<details>
<summary>Click to expand</summary>

### Easy
1. Check palindrome.  
2. Count vowels and consonants.  
3. Reverse a string.  

### Medium
4. Longest substring without repeating characters. → Sliding window.  
5. Anagram check. → Sort or freq array.  
6. String compression.  

### Hard
7. Longest Palindromic Substring. → Expand around center.  
8. Regular Expression Matching. → DP.  
9. Minimum Window Substring. → Sliding window + hashmap.  
10. Word Break problem. → DP.  

</details>

---

## Linked Lists
<details>
<summary>Click to expand</summary>

### Easy
1. Traverse and print list.  
2. Find middle node. → Fast & slow pointer.  
3. Detect cycle. → Floyd’s cycle detection.  

### Medium
4. Merge two sorted lists.  
5. Reverse a linked list.  
6. Delete nth node from end. → Two pointers.  

### Hard
7. Clone a linked list with random pointer. → HashMap.  
8. Detect intersection of two lists. → Two pointers.  
9. Sort a linked list. → Merge sort.  
10. LRU Cache design. → LinkedHashMap.  

</details>

---

## Stacks
<details>
<summary>Click to expand</summary>

### Easy
1. Implement stack using array.  
2. Balanced parentheses check.  
3. Evaluate postfix expression.  

### Medium
4. Next greater element. → Stack.  
5. Min stack (O(1) getMin).  
6. Infix to postfix conversion.  

### Hard
7. Largest rectangle in histogram. → Monotonic stack.  
8. Max rectangle in binary matrix. → Histogram approach.  
9. Celebrity problem. → Stack or two pointers.  
10. Expression evaluation with precedence.  

</details>

---

## Queues
<details>
<summary>Click to expand</summary>

### Easy
1. Implement queue using array.  
2. Implement circular queue.  
3. Implement queue using two stacks.  

### Medium
4. Sliding window maximum. → Deque.  
5. Rotten oranges problem. → BFS.  
6. First non-repeating character in stream. → Queue + freq map.  

### Hard
7. LRU Cache.  
8. Design hit counter.  
9. Maximum of all subarrays of size k.  
10. Petrol pump circular tour.  

</details>

---

## Hashing
<details>
<summary>Click to expand</summary>

### Easy
1. Count frequencies of elements.  
2. Check duplicates.  
3. Intersection of two arrays.  

### Medium
4. Subarray with sum zero.  
5. Longest consecutive sequence.  
6. Group anagrams.  

### Hard
7. Count distinct elements in every window.  
8. Find subarray with given XOR.  
9. Top K frequent elements.  
10. Largest subarray with equal 0s and 1s.  

</details>

---

## Trees
<details>
<summary>Click to expand</summary>

### Easy
1. Preorder, Inorder, Postorder traversal.  
2. Level order traversal.  
3. Height of tree.  

### Medium
4. Diameter of tree.  
5. Lowest Common Ancestor.  
6. Symmetric tree check.  

### Hard
7. Serialize & Deserialize binary tree.  
8. Maximum path sum.  
9. Construct tree from inorder & preorder.  
10. Implement Trie & search word.  

</details>

---

## Graphs
<details>
<summary>Click to expand</summary>

### Easy
1. BFS traversal.  
2. DFS traversal.  
3. Detect cycle in undirected graph.  

### Medium
4. Detect cycle in directed graph.  
5. Topological sort.  
6. Number of islands (grid traversal).  

### Hard
7. Dijkstra’s shortest path.  
8. Bellman-Ford algorithm.  
9. Kruskal’s MST.  
10. Word ladder problem.  

</details>

---

## Heaps
<details>
<summary>Click to expand</summary>

### Easy
1. Insert in MinHeap.  
2. Delete from MaxHeap.  
3. Heapify array.  

### Medium
4. Kth largest element.  
5. Merge k sorted arrays.  
6. Median from data stream.  

### Hard
7. Sliding window median.  
8. Reorganize string.  
9. Task scheduler.  
10. Minimum cost to connect ropes.  

</details>

---

## Recursion & Backtracking
<details>
<summary>Click to expand</summary>

### Easy
1. Factorial of n.  
2. Fibonacci series.  
3. Power of n^x.  

### Medium
4. Subset generation.  
5. Permutations of string.  
6. N-Queens problem.  

### Hard
7. Rat in a maze.  
8. Sudoku solver.  
9. Word search in matrix.  
10. Generate all balanced parentheses.  

</details>

---

## Dynamic Programming
<details>
<summary>Click to expand</summary>

### Easy
1. Fibonacci with DP.  
2. Climbing stairs.  
3. Min cost climbing stairs.  

### Medium
4. Longest Common Subsequence.  
5. Coin Change problem.  
6. 0/1 Knapsack.  

### Hard
7. Longest Increasing Subsequence.  
8. Edit Distance.  
9. Matrix Chain Multiplication.  
10. Maximum profit stock trading with cooldown.  

</details>

---

## Sorting & Searching
<details>
<summary>Click to expand</summary>

### Easy
1. Bubble Sort.  
2. Selection Sort.  
3. Insertion Sort.  

### Medium
4. Merge Sort.  
5. Quick Sort.  
6. Binary Search (iterative & recursive).  

### Hard
7. Search in rotated sorted array.  
8. Find peak element.  
9. Aggressive cows (binary search on answer).  
10. Allocate books problem.  

</details>

---

## Greedy Algorithms
<details>
<summary>Click to expand</summary>

### Easy
1. Activity selection problem.  
2. Minimum coins for change.  
3. Fractional knapsack.  

### Medium
4. Job scheduling problem.  
5. Huffman coding.  
6. Gas station problem.  

### Hard
7. Candy distribution.  
8. Minimum platforms.  
9. Optimal merge pattern.  
10. Interval scheduling maximization.  

</details>

---

## Sliding Window & Two Pointers
<details>
<summary>Click to expand</summary>

### Easy
1. Maximum sum subarray of size k.  
2. First negative number in every window.  
3. Count anagrams in string.  

### Medium
4. Longest substring with at most k distinct characters.  
5. Fruit into baskets.  
6. Longest repeating character replacement.  

### Hard
7. Minimum window substring.  
8. Sliding window median.  
9. Subarray product less than k.  
10. Count subarrays with k distinct integers.  

</details>

---

## Problem-Solving Patterns
<details>
<summary>Click to expand</summary>

- **Two Pointers** → Pair sum, palindrome, array merging.  
- **Sliding Window** → Longest substring, max subarray, anagrams.  
- **Binary Search on Answer** → Allocate books, aggressive cows.  
- **Greedy** → Activity selection, coin change.  
- **DP** → LIS, LCS, knapsack.  
- **Backtracking** → N-Queens, Sudoku.  

</details>

---

## ⚡ Production-Level Scenarios
- Optimize space → Use iterative DP instead of recursion.  
- Large input handling → Use `BufferedReader` instead of `Scanner`.  
- Avoid TLE → Use HashMap/HashSet instead of nested loops.  
- Handle edge cases → Empty array, single element, null checks.  
- Memory optimization → Reuse arrays, avoid unnecessary objects.  

---

## 🔥 Top 10 Frequently Asked DSA Questions
| Topic | Question | Difficulty |
|-------|----------|------------|
| Array | Maximum Subarray (Kadane) | Medium |
| Array | Trapping Rain Water | Hard |
| String | Longest Substring Without Repeating | Medium |
| Linked List | Detect Cycle | Medium |
| Stack | Largest Rectangle in Histogram | Hard |
| Queue | Sliding Window Maximum | Hard |
| HashMap | Two Sum | Easy |
| Tree | Lowest Common Ancestor | Medium |
| Graph | Number of Islands | Medium |
| DP | Longest Increasing Subsequence | Hard |

---

## ✅ Best Practices
- Always analyze **time & space complexity**.  
- Use **meaningful variable names**.  
- Modularize code into **functions/classes**.  
- Optimize using **HashMap/Set** when possible.  
- Always handle **edge cases**.  
- Write **clean, commented code**.  

---

## 🛠 Cheat Sheet
- Run Java file:  
  ```bash
  javac Main.java && java Main
  ```

- Debug with print statements.

- Use online judges: LeetCode, HackerRank, Codeforces.

- IDE shortcuts:

   - psvm → main method.

   - sout → System.out.println.
