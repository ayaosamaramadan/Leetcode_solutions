## Word Break

Given a string s and a dictionary of strings wordDict, return true if s can be segmented into a space-separated sequence of one or more dictionary words.

Note that the same word in the dictionary may be reused multiple times in the segmentation.

Example 1:

Input: s = "leetcode", wordDict = ["leet","code"]
Output: true
Explanation: Return true because "leetcode" can be segmented as "leet code".
Example 2:

Input: s = "applepenapple", wordDict = ["apple","pen"]
Output: true
Explanation: Return true because "applepenapple" can be segmented as "apple pen apple".
Note that you are allowed to reuse a dictionary word.
Example 3:

Input: s = "catsandog", wordDict = ["cats","dog","sand","and","cat"]
Output: false

## Solution

```javascript
     var wordBreak = function (s, wordDict) {
        let arr = new Array(s.length + 1).fill(false);
        arr[0] = true;
        
        for (let i = 1; i <= s.length; i++) {
          for (let j = 0; j < i; j++) {
            if (arr[j] && wordDict.includes(s.slice(j, i))) {
              arr[i] = true;
              break;
            }
          }
        }
        // console.log(arr[s.length]);
        return arr[s.length];
      };
```