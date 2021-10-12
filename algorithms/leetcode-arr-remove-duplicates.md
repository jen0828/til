## Arrays

### Remove Duplicates from Sorted Array 

```
nums = [0, 1,1,3,4,5,5,5]

def remove_duplicates(nums)
  nums.uniq!
  return nums.length
end
```