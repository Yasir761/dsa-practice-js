1. Arrays

Definition:
A collection of elements stored at contiguous memory locations.

Key Points:

Random access (O(1)) via index.

Fixed size (in most languages, e.g., C, Java).

Supports traversal, insertion, deletion, search, and update.

Time Complexity:

Access: O(1)

Search: O(n) (linear), O(log n) (if sorted + binary search)

Insertion/Deletion: O(n)

2. Linear Search

Definition:
A simple searching algorithm where we check each element one by one until we find the target.

Algorithm:

for i from 0 to n-1:
    if arr[i] == key:
        return i
return -1


Time Complexity:

Best Case: O(1) (element at start)

Worst Case: O(n) (element not found or at end)

Average: O(n/2) ≈ O(n)

Space Complexity: O(1) (no extra space).

3. Binary Search

Definition:
Efficient searching algorithm for sorted arrays that repeatedly divides the search interval in half.

Algorithm:

low = 0, high = n-1
while low <= high:
    mid = (low + high) // 2
    if arr[mid] == key:
        return mid
    else if arr[mid] < key:
        low = mid + 1
    else:
        high = mid - 1
return -1


Time Complexity:

Best Case: O(1) (mid element is target).

Worst Case: O(log n).

Average Case: O(log n).

Space Complexity:

Iterative: O(1)

Recursive: O(log n) (due to recursion stack).