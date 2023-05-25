# Move Zeroes

[Task on leetcode](https://leetcode.com/problems/move-zeroes/description/)

<details>
<summary>Task</summary>
Given an integer array nums, move all 0's to the end of it while maintaining the relative order of the non-zero elements.

Note that you must do this in-place without making a copy of the array.
</details>

<details>
<summary>Test Cases</summary>

- Input: nums = [0,1,0,3,12]<br>Output: [1,3,12,0,0]
- Input: nums = [0]<br>Output: [0]

</details>

```
class Solution {
    public void moveZeroes(int[] nums) {
        int zeros = 0;
        List<Integer> list = new ArrayList<>();
        for (int i = 0; i < nums.length; i++) {
            if (nums[i]==0){
                zeros++;
            } else {
                list.add(nums[i]);
            }
        }
        for (int i = 0; i < nums.length; i++) {
            if(i >= nums.length - zeros){
                nums[i] = 0;
                continue;
            }
            nums[i] = list.get(i);
        }
    }
}
```
