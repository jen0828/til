## Single Number
Given a non-empty array of integers nums, every element appears twice except for one. Find that single one.

You must implement a solution with a linear runtime complexity and use only constant extra space.

```
Example 1:
Input: nums = [2,2,1]
Output: 1

Example 2:
Input: nums = [4,1,2,1,2]
Output: 4

Example 3:
Input: nums = [1]
Output: 1

Constraints:

1 <= nums.length <= 3 * 104
-3 * 104 <= nums[i] <= 3 * 104
Each element in the array appears twice except for one element which appears only once.

```

```
# @param {Integer[]} nums
# @return {Integer}

def single_number(nums)
  s = Set.new
  nums.each do |n|
    if s.include?(n)
      s.delete(n)
    else
      s << n
    end
  end
  s.first
end

# use the XOR operator(^) :
#   1. a ^ 0 = 0 ^ a = a
#   2. a ^ a = 0
#   3. a ^ b ^ a = a ^ a ^ b = 0 ^ b = b


def single_number2(nums)
  nums.reduce(&:^)
end


def single_number3(nums)
  new_arr = nums.select {|num| nums.count(num) == 1}
  return new_arr.join("").to_i
end
```
