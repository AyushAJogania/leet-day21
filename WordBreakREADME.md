# leet-day21

# LeetCode Problem: Word Break

## Problem Description

Given a string `s` and a dictionary of strings `wordDict`, return true if `s` can be segmented into a space-separated sequence of one or more dictionary words.

Note that the same word in the dictionary may be reused multiple times in the segmentation.

**Example 1:**
```
Input: s = "leetcode", wordDict = ["leet","code"]
Output: true
Explanation: Return true because "leetcode" can be segmented as "leet code".
```

**Example 2:**
```
Input: s = "applepenapple", wordDict = ["apple","pen"]
Output: true
Explanation: Return true because "applepenapple" can be segmented as "apple pen apple".
```

**Example 3:**
```
Input: s = "catsandog", wordDict = ["cats","dog","sand","and","cat"]
Output: false
```

## Constraints
- `1 <= s.length <= 300`
- `1 <= wordDict.length <= 1000`
- `1 <= wordDict[i].length <= 20`
- `s` and `wordDict[i]` consist of only lowercase English letters.
- All the strings of `wordDict` are unique.

## Approach

To solve this problem, we can use dynamic programming. We can create a boolean array `dp`, where `dp[i]` represents whether the substring `s[0...i-1]` can be segmented into words from the dictionary. We initialize `dp[0]` as true since an empty string can be segmented into an empty sequence of words.

We then iterate through the string `s` from the beginning and check if any substring `s[0...i-1]` can be segmented into words from the dictionary. For each index `i`, we iterate through all the words in the dictionary and check if the substring ending at index `i` matches any of the dictionary words. If it does and the substring `s[0...i-1]` is also segmented, we set `dp[i]` as true.

Finally, we return the value of `dp[n]`, where `n` is the length of the string `s`, which represents whether the entire string can be segmented into words from the dictionary.

## Complexity Analysis

The time complexity for this approach is O(n^2) where n is the length of the string `s`. This is because for each index `i`, we iterate through all the previous indices `j` (0 <= j < i) to check if the substring `s[j...i-1]` can be segmented.

The space complexity is O(n) as we use an additional boolean array `dp` of size n+1.

## Conclusion

The solution correctly solves the problem by determining whether the given string `s` can be segmented into words from the dictionary. The dynamic programming approach efficiently handles this problem and meets the given constraints.
