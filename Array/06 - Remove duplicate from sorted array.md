# Given a sorted array, remove the duplicates in place such that each element appear only once and return the new length. Do not allocate extra space for another array, Time complexity O(n) and Space complexity O(1)

**Example:** Array = [1,1,2]

## Intution
1. j = 0. Traverse through the array with index i till n-2
2. If i-th and (i+1)-th elements are same, continue
3. If i-th and (i+1)-th elements are different, copy i-th element to j position. Increment j
4. copy (n-1) th element into j-th position. Increment j


## Algorithm
```
int removeDuplicates(vector<int>& nums) {
      //Write your code here
      
      int n = nums.size();
      int j = 0; // this will hold the position where we will place elements
      
      for(int i = 0; i < n-1; i++)
      {
          if(nums[i] != nums[i+1]) // we have found unique element
          {
              nums[j] = nums[i];
              j++;
          }
      }
      
      nums[j++] = nums[n-1]; // take care of the last element
     
      return j;
   }
```
