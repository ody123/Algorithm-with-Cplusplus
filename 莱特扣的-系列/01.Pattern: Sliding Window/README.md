#### Pattern 1 : Sliding Window (滑动窗口类型)
1. [Maximum Sum Subarray of Size K (easy) -- GeeksforGeeks](https://www.geeksforgeeks.org/find-maximum-minimum-sum-subarray-size-k/)(leetcode上未找到)
2. [Smallest Subarray with a given sum (medium) -- LeetCode](https://leetcode.com/problems/minimum-size-subarray-sum/)
3. [Longest Substring with K Distinct Characters (medium, google) -- LintCode](https://www.lintcode.com/problem/longest-substring-with-at-most-k-distinct-characters/description)
4. [Fruits into Baskets (medium) -- LeetCode](https://leetcode.com/problems/fruit-into-baskets/)
5. [No-repeat Substring (medium) -- LeetCode](https://leetcode.com/problems/longest-substring-without-repeating-characters/)
6. [Longest Substring with Same Letters after Replacement (medium, amazon) -- GeeksforGeeks](https://practice.geeksforgeeks.org/problems/maximum-sub-string-after-at-most-k-changes/0)
7. [Longest Subarray with Ones after Replacement (medium) -- GeeksforGeeks](https://www.geeksforgeeks.org/longest-subsegment-1s-formed-changing-k-0s/)(leetcode上未找到)
8. [Sliding Window Maximum (hard) -- LeetCode](https://leetcode.com/problems/sliding-window-maximum/)


# 滑动窗口  
---
*  #### 适用范围：  
通常为寻找数组中的一个满足要求的**连续**子数组， 同时满足（或不满足）这个要求的数组的任何一个子数组也一定满足（或不满足）这个要求。

*  #### 原理及特点：  
因为滑动窗口可以保证遍历到所有的满足要求连续子数组，同时因为满足（或不满足）要求的子数组的子数组也一定满足（或不满足）要求，所以无需再遍历其子数组，即滑窗的左右指针每次只需向右移动，这样保证了数组的每个元素最多被访问2次，所以时间复杂度为O(n)。  

*  #### 通用解法：  
使用双指针滑动窗口，初始化目标值以及窗口两边的指针l, r=0, 1，滑动窗口可以直接用原数组切片表示。  (可以直接初始化一个空窗口两端都为0，然后每次右移判断，初始化0，1相当于先单独初始化了一个0到1的窗口，同时还要单独判断这个窗口，没有整合到while中去）
构造一个while循环体
对右指针从1到最后的每一个位置判断当前窗口是否满足要求，满足要求则更新目标值, 同时根据情况更新指针以及辅助变量。（**注意如果右指针在最后一个位置时，要防止右指针继续向右移动**） 
循环结束后返回目标值
