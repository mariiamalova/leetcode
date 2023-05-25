# Squares of a Sorted Array

[Task on leetcode](https://leetcode.com/problems/squares-of-a-sorted-array/description/)

<details>
<summary>Task</summary>
Given an integer array nums sorted in non-decreasing order, return an array of the squares of each number sorted in non-decreasing order.
</details>
<details>
<summary>Test Cases</summary>

- Input: nums = [-4,-1,0,3,10]<br>Output: [0,1,9,16,100]
- Input: nums = [-7,-3,2,3,11]<br>Output: [4,9,9,49,121]

</details>

```
class Solution {
     public int[] sortedSquares(int[] nums) {
        int left = 0;
        int right = nums.length - 1;
        int i = nums.length - 1;
        int[] res = new int[nums.length];

        while (left<=right){
            int leftsq = nums[left] * nums[left];
            int rightsq = nums[right] * nums[right];

            if (leftsq > rightsq){
                res[i]  = leftsq;
                left++;
            } else {
                res[i] = rightsq;
                right--;
            }
            i--;
        }
        return res;
    }
}
```