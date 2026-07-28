# Two Sum

![Difficulty](https://img.shields.io/badge/Difficulty-Easy-22c55e?style=flat-square)
![Platform](https://img.shields.io/badge/Platform-LeetCode-c2572b?style=flat-square)
![Language](https://img.shields.io/badge/Language-C%2B%2B-0284c7?style=flat-square)

[View Problem on LeetCode](https://leetcode.com/problems/two-sum/submissions/2084701163/)

---


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
