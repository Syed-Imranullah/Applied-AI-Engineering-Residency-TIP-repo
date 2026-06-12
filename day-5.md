# Day 5

Problem: 
leetcode link: https://leetcode.com/problems/3sum/

```js
//js solution
function threeSum(nums) {
  const result = [];
  nums.sort((a, b) => a - b);
  for (let i = 0; i < nums.length - 2; i++) {
    if (i > 0 && nums[i] === nums[i - 1]) continue;
    let left = i + 1;
    let right = nums.length - 1;
    while (left < right) {
      const sum = nums[i] + nums[left] + nums[right];
      if (sum === 0) {
        result.push([nums[i], nums[left], nums[right]]);
        while (left < right && nums[left] === nums[left + 1]) left++;
        while (left < right && nums[right] === nums[right - 1]) right--;
        left++;
        right--;
      } else if (sum < 0) {
        left++;
      } else {
        right--;
      }
    }
  }
  return result;
}
```
Input: nums = [-1,0,1,2,-1,-4]
Output: [[-1,-1,2],[-1,0,1]]

Algorithm: Sort the array, then loop through each number while fixing one element at a time. For each fixed number, use two pointers starting from the next index and the end of the array to find two numbers that sum with it to zero. Calculate the total of the three numbers, and if the total equals zero, add the triplet to the result and move both pointers inward while skipping duplicates. If the total is less than zero, move the left pointer to the right to increase the sum, and if the total is greater than zero, move the right pointer to the left to decrease the sum. Continue this process for each element in the array while skipping duplicate fixed numbers, then return the list of unique triplets.


Python Solution:

```py
# solution here
class Solution(object):
    def threeSum(self, nums):
        """
        :type nums: List[int]
        :rtype: List[List[int]]
        """
        
        result = []
        nums.sort()

        for i in range(len(nums) - 2):
            if i > 0 and nums[i] == nums[i -1]:
                continue
            left = i + 1
            right = len(nums) -1
            while left < right:
                total = nums[i] + nums[left] + nums[right]
                if total == 0:
                    result.append([nums[i], nums[left], nums[right]])
                    while left < right and nums[left] == nums[left + 1]:
                        left += 1
                    while left < right and nums[right] == nums[right - 1]:
                        right -= 1
                    left += 1
                    right -= 1
                elif total < 0:
                    left += 1   
                else:
                    right -= 1
        
        return result
```
