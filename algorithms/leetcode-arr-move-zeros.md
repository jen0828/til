## Move Zeros

Given an integer array nums, move all 0's to the end of it while maintaining the relative order of the non-zero elements.

Note that you must do this in-place without making a copy of the array.
 
```
Example 1:

Input: nums = [0,1,0,3,12]
Output: [1,3,12,0,0]

Example 2:

Input: nums = [0]
Output: [0]
```

```
# @param {Integer[]} nums
# @return {Void} Do not return anything, modify nums in-place instead.

def move_zeroes(nums)
  zero_count = nums.count(0)
  nums.delete(0)
  nums.concat(Array.new(zero_count, 0))
end

```