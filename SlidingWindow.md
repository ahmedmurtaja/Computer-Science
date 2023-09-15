# Sliding Window Technique

## What is Sliding Window Technique?
Sliding Window Technique is a technique that uses a **window** to solve a problem.
The window is a range of elements in the array,The window **slides** over the array to solve the problem

![Alt text](https://res.cloudinary.com/practicaldev/image/fetch/s--wLHE9zdk--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_66%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/i/083uadwx1ldawxgsexpo.gif)
## When to use Sliding Window Technique?
Sliding Window Technique is used to solve problems that involve finding a subset of the array that satisfies a certain condition.

## How to use Sliding Window Technique?
1. Define the window
2. Initialize the window
3. Slide the window
4. Update the result

## Example
### Problem
Given an array of integers, find the maximum sum of a sub-array of size k.

### Solution
```js=
function maxSum(arr, k) {
  let i = 0;
  let j = k - 1;
  let sum = 0;
  for (let x = 0; x < k; x++) {
    sum += arr[x];
  }
  let max = sum;
  while (j < arr.length - 1) {
    sum -= arr[i];
    i++;
    j++;
    sum += arr[j];
    max = Math.max(max, sum);
  }
  return max;
}
```
The above function is a function that finds the maximum sum of a subarray of size k. For example, the maximum sum of a subarray of size 3 in the array [1, 2, 3, 4, 5, 6, 7, 8, 9] is 7 + 8 + 9 = 24.

### Explanation
The above function uses the sliding window technique to solve the problem. The window is a range of elements in the array. The window slides over the array to solve the problem. The window is defined by the following variables:
- `i`: the index of the first element in the window
- `j`: the index of the last element in the window

The window is initialized as follows:
- `i = 0`
- `j = k - 1`

The window slides as follows:
- `i++`
- `j++`

The result is updated as follows:
- `max = Math.max(max, sum)`


### Time Complexity
The time complexity of the above function is O(n) where n is the length of the array.

### Space Complexity
The space complexity of the above function is O(1).

## Practice
- [Maximum Sum Subarray of Size K](https://leetcode.com/problems/maximum-subarray/)
- [Longest Substring Without Repeating Characters](https://leetcode.com/problems/longest-substring-without-repeating-characters/)

## References
- [Sliding Window Technique](https://www.geeksforgeeks.org/window-sliding-technique/)
- [YouTube](https://www.youtube.com/watch?v=MK-NZ4hN7rs)
