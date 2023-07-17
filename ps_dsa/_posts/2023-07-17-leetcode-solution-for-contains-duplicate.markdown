---
layout: post
title:  "Leetcode solution for Contains Duplicate"
date:   2023-07-17 12:23:48 +0900
category: ps_dsa
---

![Keypad](/ps_dsa/assets/images/leetcode.png)

# [Contains Duplicate](https://leetcode.com/problems/contains-duplicate/)

Given an integer array nums, return true if any value appears at least twice in the array, and return false if every element is distinct.


## Sample input output
{% highlight python %}

  Example 1:

  Input: nums = [1,2,3,1]
  Output: true
  Example 2:

  Input: nums = [1,2,3,4]
  Output: false
  Example 3:

  Input: nums = [1,1,1,3,3,4,3,2,4,2]
  Output: true

{% endhighlight %}

## Solution

{% highlight python %}

  class Solution:
      def containsDuplicate(self, nums: List[int]) -> bool:
          return len(nums) != len(set(nums))

{% endhighlight %}


Congratualtions. Problem is solved.

Happy coding :)

