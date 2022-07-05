# Write an algorithm to find out next greater number to given number with the same set of digits

**Example:** 218765

## Intution
1. identify the digit (say at i-th position) which is smaller than the last digit ((n-1)-the position).
2. Swap these two digits -> i-th position and (n-1)-the position.
3. Sort the portion of the array from i + 1 till n-1

## Algorithm

```
void findNext(char array1[], int n) 
{ 
    // traverse from last
     int i = n-1;
     for(; i >= 0; i--)
     {
        find the first digit from the right that is less than the last digit
         if(array1[i] < array1[n-1])
             break;
     }
     
     /// swap the samller digit with last digit
     swap(array1[i], array1[n-1]);
     
     // sort the array towards the right of the digit
     sort(array1 + i + 1, array1 + n);
     
    return; 
} 
```
