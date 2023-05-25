# Summary Ranges

[Task on leetcode](https://leetcode.com/problems/summary-ranges/description/)

<details>
<summary>Task</summary>
You are given a sorted unique integer array nums.

A range [a,b] is the set of all integers from a to b (inclusive).

Return the smallest sorted list of ranges that cover all the numbers in the array exactly. That is, each element of nums is covered by exactly one of the ranges, and there is no integer x such that x is in one of the ranges but not in nums.

Each range [a,b] in the list should be output as:

- "a->b" if a != b
- "a" if a == b
</details>

<details>
<summary>Test Cases</summary>

- Input: nums = [0,1,2,4,5,7]"<br>Output: ["0","2->4","6","8->9"]
- Input: nums = [0,1,2,4,5,7]<br>Output: ["0->2","4->5","7"]

</details>

```
class Solution {
     public List<String> summaryRanges(int[] nums) {
        int currentFirst = 0;
        int currentSecond = 0;
        boolean flag = true;
        List<String> result = new ArrayList<>();
        for (int i = 0; i < nums.length; i++) {
            if (flag) {
                currentFirst = nums[i];
            }
            if (i == nums.length - 1 ) {
                currentSecond = nums[i];
                addInResult(currentFirst, currentSecond, result, flag);
                break;
            } if (nums[i] < nums[i] + 1){
                currentSecond = nums[i];
            }
            if (nums[i + 1] == nums[i] + 1) {
                currentSecond = nums[i + 1];
                flag = false;
            } else {
                flag = addInResult(currentFirst, currentSecond, result, flag);
            }
        }
        return result;
    }
    private static boolean addInResult(int currentFirst, int currentSecond, List<String> result, boolean flag) {
        if (currentFirst == currentSecond) {
            result.add(currentFirst + "");
            flag = true;
        } else {
            result.add(currentFirst + "->" + currentSecond);
            flag = true;
        }
        return flag;
    }
}
```