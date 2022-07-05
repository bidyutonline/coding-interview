# Array consist of only 0's, 1's and 2's. Write an algorithm to sort  this array in O(n) time complexity and O(1) Space complexity with only one traversal

**Example:**  [0 1 2 0 1 2]

## Intution
1. There are only three elements 0, 1 and 2.
2. While traversing the array, put 0's towards beginging of the array
3. While traversing the array, put 2's towards the end of the array
4. While traversing the array, if we face 1, do nothing. 

## Algorithm
```
low = 0, high = size - 1, mid = 0

while mid <= high
  if arr[mid] == 0
    swap (arr[mid], arr[low])
    low++
    mid++
  else if arr[mid] == 2
    swap(arr[mid], arr[high])
    high--
  else //encountered 1, do nothing
    mid++;

```
