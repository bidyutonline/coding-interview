# Problem: Find the maximum element in an array which is first increasing and then decreasing.

**Example:** 6 9 15 25 35 50 41 29 23 8

## Intution

There are three types of element

1. First half is increasing. The elements in first half has the property that the previous element is less than the element and the next element is greater than the element.
- *i.e a[i-1] < a[i] < a[i + 1] for any i in first half*

2. Second half is decreasing. The elements in the second half has the property that the previous is greater than the element and the element is greater than the next element.
- *i.e. a[i - 1] > a[i] > a[i + 1] for any i in second half*
 
3. The maximum element is in between these two half. It has property that the elements in both side is lesser than the element.
- *i.e. a[i - 1] < a[i] > a[i + 1] if a[i] is maximum.*
      
4. Use these properties and perform **binary search**.
  
      
## Algorithm
```
  1. find mid = (low + high)/2
  2. if arr[mid -1] < arr[mid] && arr[mid] > arr[mid + 1] 
  3.   then return mid as this is the maximum element
  4. if arr[mid - 1] < arr[mid] && arr[mid] < arr[mid + 1] 
  5.   then mid is in left half, call function in recursion for (mid + 1) and high
  6. if arr[mid -1 ] > arr[mid] and arr[mid] > arr[mid + 1]
  7.   then mid is in right half, call function in recursion for low and (mid -1)
``` 
