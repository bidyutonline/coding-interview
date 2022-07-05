# You have an array of non-negative integers,you are initially positioned at the first index of the array.Each element in the array represents your maximum jump length at that position.Determine if you are able to reach the last index in O(n) Time complexity and O(1) Space Complexity 

**Example:** A = [2,3,1,1,4]

## Intution
1. Traverse trough the array once
2. Each element in the array is number of steps we can take forward
3. When curren step is exausted increase jump

## Algorithm

```
int minJumpToReachEnd(int array1[], int n) 
{ 
     int a = array1[0], b = array1[0], jump = 1;
     
     for(int i = 1; i <n; i++)
     {
         a--;
         b--;
         
         if (i == n-1) // We have reached last element
         {
             return jump;
         }
         
         if(array1[i] > b) // we have found a value with greater steps
         {
             b = array1[i];
         }
         
         if(a == 0) // Steps has exhaused, so we need a jump
         {
             a = b;
             jump++;
         }
     }

    return jump; 
} 
```
