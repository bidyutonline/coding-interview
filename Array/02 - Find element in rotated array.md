# Find a element from an array that is sorted and then rotated.

**Example:** array[] = {7 8 9 10 1 2 3 4 5 6} , key = 5

## Intution

1. The arrange has two segments - left segment and right segment
2. If an element is greater that the first element of array, then the element is in left segment.
3. If the element is less than the first element, then the element is in the right segment
4. Use this information and perform **binary search**

## Algorithm

```
mid = (low + high)/2

if arr[mid] == key  //we have found it
  return mid
  
if array[mid] > array[low] // the mid is in left segment
    if key >= arr[low] && key <= arr[mid]  // key is in left segment
        call recursive function with low, (mid - 1)
    else
        call recursive function with (mid + 1), high
      
if array[mid] < array[high] // the mid is in second half
    if key >= array[mid] && key <= array[high] // key is in right segment
        call recursive function with (mid + 1) and high
    else
        call recursive function with low, mid - 1
```
