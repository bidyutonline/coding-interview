# List of arrival and departure time is given, Find the minimum number of platforms are required for the railway as no train waits

**Example:** Arrivals = [200, 210, 300, 320, 350, 500] Depertures = [230, 340, 320, 430, 400, 520] Plaforms expected = 3

## Intution
1. Sort the arrivals array
2. Sort the deperture array
3. for each train arrving, check if any train left just before that.
4. If not increase platform requirement
5. If yes, decrease plaform requirement
6. Output max platform requirement encountered.

## Algorithm
```
int minPlatform(int arrival[], int departure[], int n) {
   //Practise Yourself : Write your code Here
   
   sort(departure, departure + n);
   
   int i = 1, j = 0, platform = 1, maxPlatform = 1;
   
   while (i < n && j < n)
   {
       if(arrival[i] < departure[j]) // There is no available empty platform
       {
           platform++;
           i++;
           if(platform > maxPlatform)
               maxPlatform = platform;
       }
       else // one empty platform is available
       {
           platform--;
           j++;
       }
   }
   return maxPlatform;
}
```
