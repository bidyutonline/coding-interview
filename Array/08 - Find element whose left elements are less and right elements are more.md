# We have an array, we have to find an element before which all elements are less than it, and after which all are greater than it. Finally, return the index of the element, if there is no such element, then return -1: Time complexity O(n) and Space Complexity O(n)

**Example:** arr[] = {5, 1, 4, 3, 6, 8, 10, 7, 9} output 4

## Intution
1. Scan from left, keep a max element and keep updated as we go
2. continue until we find an element which is greater than all left elements.
3. Start new scan from here to check all elements in the right are greater

## Algorithm

```
int findElement(int arr[], int n) 
{ 
    //Write your code here 
    int leftmax = 0;
    int i = 0;
    
    for(; i < n; i++)
    {
        if(leftmax < arr[i] && arr[i] < arr[i+1])
            break;
            
        if(arr[i] > leftmax)
        {
            leftmax = arr[i];
        }
    }
        
    for (int j = i + 1; j < n; j++)
    {
        if( arr[j] < arr[i])
            return -1;
    }
    
    if(i >= n) return -1;
    return i; 
} 
```
