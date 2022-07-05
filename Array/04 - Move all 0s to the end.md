# Given an array nums, write a function to move all 0's to the end of it while maintaining the relative order of the non-zero elements in O(n) Time complexity and O(1) Space complexity with single traversal allowed

**Example:** [0,1,0,3,12]

## Intution
1. Remove all positive numbers towards left.
2. 0's will be moved towards right automatically

## Algorithm
```
i = 0, pos = 0
while ( i < size)
    if arr[i] == 0
        i++
    else if arr[i] > 0
        if(i != pos)
            swap(arr[i], arr[pos])
            i++
            pos++
        else // no point of swapping if i and pos are pointing to same location
            i++
```
