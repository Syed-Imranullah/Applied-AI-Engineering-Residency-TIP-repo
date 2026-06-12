# Day 4

Problem: 
leetcode link: https://leetcode.com/problems/group-anagrams/

```js
//js solution
javascript
function groupAnagrams(strs) {
  const map = {};
  for (let i = 0; i < strs.length; i++) {
    const key = strs[i].split('').sort().join('');
    if (map[key] === undefined) {
      map[key] = [];
    }
    map[key].push(strs[i]);
  }
  return Object.values(map);
}
```
Input: strs = ["eat","tea","tan","ate","nat","bat"]

Output: [["bat"],["nat","tan"],["ate","eat","tea"]]

Algorithm: Create an empty object, then loop through the strings in strs. For each string, split it into characters, sort them, and join them back together to form a key. If the key does not exist in the object, initialize it with an empty array, then push the original string into that array. If the key already exists, simply append the string to the existing array. After processing all strings, return the values of the object.


Python Solution:

```py
# solution here
class Solution(object):
    def groupAnagrams(self, strs):
        """
        :type strs: List[str]
        :rtype: List[List[str]]
        """
        map = {}
        for word in strs:
            key = "".join(sorted(word))
            if key not in map:
                map[key] = []
            map[key].append(word)

        return list(map.values())

```
