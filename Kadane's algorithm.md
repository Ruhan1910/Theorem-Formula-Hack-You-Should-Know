Kadane's Algorithm is a dynamic programming technique used to find the maximum sum of a contiguous subarray within a given array of numbers. 
It efficiently solves the "maximum subarray problem" with a time complexity of O(n), making it significantly faster than brute-force approaches

**Here's a breakdown of how it works:**

**1. Initialization:**

#globalSum: Stores the maximum sum found so far (initialized to negative infinity or the first element of the array if all elements are negative).

#currSum: Stores the maximum sum ending at the current position (initialized to 0).

**2. Iteration:**

-Iterate through the array:

  -For each element:
  
    -Add the current element to currSum.
    
    -If currSum is greater than globalSum, update globalSum with currSum.
    
    -If currSum becomes negative, reset it to 0 (as a negative subarray sum will not contribute to a larger maximum).
    
**3. Result:**

After iterating through the entire array, globalSum will hold the maximum sum of any contiguous subarray. 

Resourses: [link](https://en.wikipedia.org/wiki/Maximum_subarray_problem)
