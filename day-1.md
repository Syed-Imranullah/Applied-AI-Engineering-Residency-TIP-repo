# Day 1

Problem: FizzBuzz

leetcode link: https://leetcode.com/problems/fizz-buzz/

```js
function fizzBuzz(n) {
  const result = [];
  for (let i = 1; i <= n; i++) {
    if (i % 15 === 0) {
      result.push('FizzBuzz');
    } else if (i % 3 === 0) {
      result.push('Fizz');
    } else if (i % 5 === 0) {
      result.push('Buzz');
    } else {
      result.push(String(i));
    }
  }
  return result;
}
```
Input: n = 3
Output: ["1","2","Fizz"] 

Algorithm: 

Create a empty list result

loop through each number from 1 - n

if the number is divisible by 5 and 3 print "FizzBuzz"

otherwise if the number is divisible by 3 add "Fizz" to result
otherwise if the number is divisible by 5 add "Buzz" to result

if none of the above conditions are true then convert the number into the string and add it to the result

return completed list






Python Solution:

```py
# solution here

class Solution(object):
    def fizzBuzz(self, n):
        result = []

        for i in range(1, n + 1):
            if i % 15 == 0:
                result.append("FizzBuzz")
            elif i % 3 == 0:
                result.append("Fizz")
            elif i % 5 == 0:
                result.append("Buzz")
            else:
                result.append(str(i))

        return result
```
