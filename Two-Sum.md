# Two Sum


[Task on leetcode](https://leetcode.com/problems/two-sum/description/)
<details>
<summary>Task</summary>
Given an array of integers nums and an integer target, return indices of the two numbers such that they add up to target.
You may assume that each input would have exactly one solution, and you may not use the same element twice.
You can return the answer in any order.
</details>
<details>
<summary>Test Cases</summary>

- Input: nums = [2,7,11,15], target = 9<br>Output: [0,1]
- Input: nums = [3,2,4], target = 6<br>Output: [1,2]

</details>

```
class Solution {
   public int[] twoSum(int[] nums, int target) {
        int[] res = new int[2];
        for (int i = 0; i < nums.length; i++) {
            for (int j = 0; j < nums.length; j++) {
                if (i != j) {
                    if (nums[i] + nums[j] == target) {
                        res[0] = i;
                        res[1] = j;
                        return res;
                    }
                }
            }
        }
        return res;
    }
}
```

