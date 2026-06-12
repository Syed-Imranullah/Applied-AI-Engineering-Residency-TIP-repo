# Day 3

Problem: 
leetcode link: https://leetcode.com/problems/reverse-string/

```js
//js solution
function reverseString(s) {
  let left = 0;
  let right = s.length - 1;
  while (left < right) {
    let temp = s[left];
    s[left] = s[right];
    s[right] = temp;
    left++;
    right--;
  }
  return s;
}
```
Input: s = ["h","e","l","l","o"]
Output: ["o","l","l","e","h"]


Algorith: two pointers, left starting at 0 and right starting at the end, swap and move both towards the middle until they meet


Python Solution:

```py
# solution here
class Solution(object):
    def reverseString(self, s):
        """
        :type s: List[str]
        :rtype: None Do not return anything, modify s in-place instead.
        """
        left = 0
        right = len(s) - 1
        while left < right:
            temp = s[left]
            s[left] = s[right]
            s[right] = temp
            left += 1
            right -= 1

          

```
