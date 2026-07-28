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
- **Key Idea**: The solution iterates through the input array, storing each element and its index in a hash table. Then, for each element, it checks if its complement (target - current element) exists in the hash table and is not the same index. If found, it returns the indices of the two elements.

- **Considerations**: The solution assumes that the input array has a unique solution. If there are multiple solutions, this approach will only return one of them. Additionally, the solution does not handle the case where the input array is empty or has only one element.
- **Optimization Notes**: The solution has a time complexity of O(N) because it iterates through the input array twice. The hash table operations (insertion and lookup) have an average time complexity of O(1).

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
