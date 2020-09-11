---
layout: post
title: Leetcode152 Maximum Product SubArray
categories: Leetcode
description: 2020 September 11 Daily challenge
keywords: Leetcode, DynamicProgramming, medium, Array
---

## [Leetcode152] Maximum Product SubArray Solution

-----------------------------------------------------------------------------

    | #   | Title                    | Difficulty |    Tag    |
    | --- | :----------------------- | ---------: | :-------: |
    | 152 | Maximum Product SubArray |     Medium | Array, DP |

### Solution1: Brute Force

```Java
// O(n * n) time complexity to loop the array twice and find the max product subarray
class Solution {
    // Brute Force: use two loop to find the max result 
    public int maxProduct(int[] nums) {
        if(nums == null || nums.length <= 0) return 0;
        
        long result = nums[0];
        for(int i = 0; i < nums.length; i++){
            int product = 1;
            for(int j = i; j < nums.length; j++){
                product *= nums[j];
                result = Math.max(result, product);
            }
        }
        return (int)result;
    }
}
```

### Solution2: Dynamical Programming

```Java
class Solution {
    // The result would be in three possible values going on
    // cur: Current value
    // maxSoFar: positive accumulate values
    // minSoFar: for a possible negative min value
    public int maxProduct(int[] nums) {
        if(nums == null || nums.length <= 0) return 0;

        int maxSoFar = nums[0];
        int minSoFar = nums[0];
        int result = maxSoFar;
        
        for(int i = 1; i < nums.length; i++){
            int cur = nums[i];
            int tempMax = Math.max(cur, Math.max(maxSoFar * cur, minSoFar * cur));
            minSoFar = Math.min(cur, Math.min(maxSoFar * cur, minSoFar * cur));
            
            maxSoFar = tempMax;
            result = Math.max(maxSoFar, result);
        }
        
        return result;
    }
}
```
