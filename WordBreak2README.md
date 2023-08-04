# leet-day21

# Word Break II - LeetCode Problem

## Problem Description

Given a string `s` and a dictionary of strings `wordDict`, you need to add spaces in `s` to construct a sentence where each word is a valid dictionary word. Return all such possible sentences in any order.

Note that the same word in the dictionary may be reused multiple times in the segmentation.

## Example

### Input

```
s = "catsanddog"
wordDict = ["cat","cats","and","sand","dog"]
```

### Output

```
["cats and dog","cat sand dog"]
```

### Explanation

In the given example, we can form two valid sentences using words from the `wordDict`. The possible sentences are "cats and dog" and "cat sand dog".

## Constraints

- 1 <= s.length <= 20
- 1 <= wordDict.length <= 1000
- 1 <= wordDict[i].length <= 10
- s and wordDict[i] consist of only lowercase English letters.
- All the strings of wordDict are unique.
- The length of the answer doesn't exceed 10^5.

## Approach and Implementation

To solve this problem, we use backtracking to generate all possible sentences by adding spaces to the input string `s` in different ways. We start by considering each word from the `wordDict` and see if it matches the prefix of the remaining string. If it matches, we add the word to the current sentence and recursively continue with the remaining suffix of the string. We keep track of all possible sentences and return them as the result.

We implement the solution in C++ using a helper function `backtrack`. We use a set to store the words from `wordDict` for quick lookup. The helper function takes the input string `s`, the current index `start` where we start checking for words, the word dictionary `dict`, the current sentence being constructed, and the result vector to store the final sentences.

The `backtrack` function is called recursively, and it checks for all possible words that can be formed starting from the `start` index. If a word is found in the `wordDict`, we add it to the current sentence and continue recursively with the remaining string. When the `start` index reaches the end of the string, we have formed a valid sentence, and we add it to the result vector.

Finally, we call the `wordBreak` function, passing the input string `s` and the word dictionary `wordDict`. It returns a vector of strings containing all possible sentences formed by adding spaces to `s`.

## Complexity Analysis

The time complexity of the solution is O(2^n), where n is the length of the input string `s`. This is because in the worst case, we have 2^n possible ways to add spaces to the string, forming all possible sentences. However, the actual time complexity may be lower than the worst case due to backtracking.

The space complexity is O(n), where n is the length of the input string `s`. This is because we use a recursive call stack to store the intermediate results during backtracking. Additionally, the set `dict` stores the words from the word dictionary, which may have a space complexity of O(k), where k is the total length of all words in the dictionary.

## Summary

The problem involves adding spaces to a string to construct sentences using words from a given dictionary. We use backtracking to generate all possible sentences and store them in a vector, which is then returned as the final output. The solution is implemented in C++ and follows the constraints specified in the problem description.
