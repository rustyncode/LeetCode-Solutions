# Two Sum

![Difficulty](https://img.shields.io/badge/Difficulty-Easy-22c55e?style=flat-square)
![Platform](https://img.shields.io/badge/Platform-LeetCode-c2572b?style=flat-square)
![Language](https://img.shields.io/badge/Language-C%2B%2B-0284c7?style=flat-square)

[View Problem on LeetCode](https://leetcode.com/problems/two-sum/submissions/2084701163/)

---

## Solution Overview

- **Approach**: `Hash Table`
- **Time Complexity**: `O(N)`
- **Space Complexity**: `O(N)`
- **Key Idea**: The key idea is to build a hash table that maps each number in the input array to its index. Then, for each number, we calculate its complement with respect to the target sum and check if the complement exists in the hash table. If it does, and the indices are different, we return the pair of indices.

- **Considerations**: When building the hash table, we consider the case where the input array contains duplicate numbers. In this case, we need to ensure that we return the correct pair of indices. Additionally, we need to consider the case where the input array is empty or contains only one element, in which case there is no solution.
- **Optimization Notes**: The time complexity of the solution is O(N) because we are iterating over the input array twice: once to build the hash table and once to find the complement. The hash table operations (insertion and lookup) take constant time on average, so they do not affect the overall time complexity.

## Source Code (C++)

```cpp
class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) {
        unordered_map<int, int> numMap;
        int n = nums.size();
        // Build the hash table
        for (int i = 0; i < n; i++) {
            numMap[nums[i]] = i;
        }
        // Find the complement
        for (int i = 0; i < n; i++) {
            int complement = target - nums[i];
            if (numMap.count(complement) && numMap[complement] != i) {
                return {i, numMap[complement]};
            }
        }
        return {}; // No solution found
    }
};
```

---
*Synced automatically with [Rustyn Analyzer](https://analzer.rustyn.me/)*
