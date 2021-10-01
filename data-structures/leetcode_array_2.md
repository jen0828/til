## Rotate Array
Given an array, rotate the array to the right by k steps, where k is non-negative.

```
# @param {Integer[]} nums
# @param {Integer} k
# @return {Void} Do not return anything, modify nums in-place instead.

def rotate(nums, k)
  (k % nums.count).times do
    nums.insert(0, nums.pop)
  end
end

def rotate2(nums, k)
  k = k % nums.count
  nums[0..-1] = nums[-k..-1] + nums[0...-k]
end

def rotate3(nums, k)
  k = k % nums.count if k > nums.count

  reverse(nums, 0, nums.count - 1)
  reverse(nums, 0, k - 1)
  reverse(nums, k, nums.count - 1)

  return
end
  
def reverse(nums, first, last)
  while first < last
    nums[first], nums[last] = nums[last], nums[first]

    first += 1
    last -= 1
  end
end

```