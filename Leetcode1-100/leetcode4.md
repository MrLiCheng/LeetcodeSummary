  
# LeetCode 问题 4：寻找两个正序数组的中位数

题目难度为 Easy

### 题目描述

给定两个大小为 m 和 n 的正序（从小到大）数组 `nums1` 和 `nums2`，请你找出这两个正序数组的中位数，并且要求算法的时间复杂度为 O(log(m + n))。

你可以假设 `nums1` 和 `nums2` 不会同时为空。

**示例:**

```
nums1 = [1, 3]
nums2 = [2]

则中位数是 2.0
```

```
nums1 = [1, 2]
nums2 = [3, 4]

则中位数是 (2 + 3)/2 = 2.5
```

### 解题思路

使用查找表来解决该问题

### 精选代码

```
class Solution {
    
    public int[] twoSum(int[] nums, int target) {
        HashMap<Integer, Integer> hm = new HashMap<Integer, Integer>();
        for(int i = 0; i < nums.length; i++){
            if(hm.containsKey(target - nums[i]))
                return new int[] {i, hm.get(target - nums[i])};
            else hm.put(nums[i], i);
        }
        return new int[0];
    }
    
}
```
