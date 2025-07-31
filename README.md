# leetcode-patterns
## documenting all patterns of leetcode problems with solutions 
### Patterns :
1. Sliding Window
2. Subset
3. Binary Search modified
4. Top k elements
5. DFS Binary tree
6. Topological sort
7. Binary tree BFS
8. 2 pointers

### sliding window:
so the logic is that the 2 pointers maintain a "window" over part of the input - substring of the input. they expand or shrink window depending on the conditions.
when do you use it ?
mostly when there are substrings or subarrays to be checked, and problems that ask for max/min length or sum or diff that satisfies some condition.
template: expand right pointer, shrink left pointer when condition breaks

this is a dry run for how the code works for: find longest substring with K unique characters in a given string
- what are we finding? the length of the subtring that has k=3 unique characters. the condition where we shrink? when cnt>k - whenever count of unique characters read becomes more than k specified then we shrink and remove previous unique characters.
![WhatsApp Image 2025-07-31 at 12 58 25_6b78ddab](https://github.com/user-attachments/assets/3fb22bd2-4005-4778-8588-feeb41b6331d)

### subset:
we are looking for combinations of elements- we either choose or not choose each element at every step 
used for backtracking problems.
template: DFS recursion: at each index, choose or skip, add path to result, backtrack 
"generate all combinations", "return all possible sequences", "find all permutations", etc.

### modified binary search 
the array is already sorted now we compare the mid element to see which half to work on. 

### top k elements
when to use: need largest or smallest k items, or k-th value 
template: use heap or priority queue, sometimes quicksort works too

### DFS binary search 
when: problems with sorted decision space but graph or tree exploration 
template: use DFS to check feasibility combined with binary search on value

### topo sort
when: directed acyclic graph, nested connections but not looping, ordering, prerequisties
template: compute in-degree, sue BFS- kahn'salgo or DFS stack

### binary tree BFS
when: tree problems that require level order or shortest path
template: use queue data structure, process root node so that u access to child nodes, remove root, this makes sure that you always have the left next accessible child node at the front of the queue

### 2 pointers
when: sorted arrays, linked lists, string problems, pairs,moving ends
template: use 2 pointers one at the front and one at end and keep moving them based on condition

here p1 is at front and p2 at end. our goal is to find the index of numbers in the sorted array that sum up to be 18= target. 
1st pass = p1(2)+p2(15) = 17 -> 17 < target -> move p1 forward 
2nd pass = p1(7)+p2(15) = 22 -> 22 > target -> move p2 backward 
3rd pass = p1(7)+p2(11) = 18 -> 18 = target -> condition met 
loop breaks, return p1 and p2 (index)
![WhatsApp Image 2025-07-31 at 13 16 56_89e3def1](https://github.com/user-attachments/assets/d21d563b-0535-43e7-b8d9-7958da16fb0f)

