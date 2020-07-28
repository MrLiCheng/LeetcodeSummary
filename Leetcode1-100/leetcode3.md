  
# LeetCode 问题 3：两数之和

题目难度为 Easy

### 题目描述

给定一个字符串，请你找出其中不含有重复字符的 **最长子串** 的长度。

**示例:**

```
输入: "abcabcbb"
输出: 3 
解释: 因为无重复字符的最长子串是 "abc"，所以其长度为 3。
```

```
输入: "bbbbb"
输出: 1
解释: 因为无重复字符的最长子串是 "b"，所以其长度为 1。
```

```
输入: "pwwkew"
输出: 3
解释: 因为无重复字符的最长子串是 "wke"，所以其长度为 3。请注意，你的答案必须是 子串 的长度，"pwke" 是一个子序列，不是子串。
```

### 解题思路

通过map的key唯一性快速找到最近的字母出现的位置

### 精选代码

```
class Solution {
    
    public int lengthOfLongestSubstring(String s) {
        Map<Character, Integer> hm = new HashMap<>();
        int max = 0;
        //双指针：快指针指向最新的下标，慢指针指向不重复的最小下标
        for (int i = 0, j = 0; i < s.length(); i++) {
            if (hm.containsKey(s.charAt(i))) {
                j = Math.max(j, hm.get(s.charAt(i)));
            }
            max = Math.max(max, i - j + 1);
            hm.put(s.charAt(i), i + 1);
        }
        return max;
    }
    
}
```
