# Two Sum II - Input Array Is Sorted

[Task on leetcode](https://leetcode.com/problems/two-sum-ii-input-array-is-sorted/description/)
<details>
<summary>Task</summary>
Given a 1-indexed array of integers numbers that is already sorted in non-decreasing order, find two numbers such that they add up to a specific target number. Let these two numbers be numbers[index1] and numbers[index2] where 1 <= index1 < index2 <= numbers.length.
<br>Return the indices of the two numbers, index1 and index2, added by one as an integer array [index1, index2] of length 2.
<br>The tests are generated such that there is exactly one solution. You may not use the same element twice.
Your solution must use only constant extra space.
</details>
<details>
<summary>Test Cases</summary>

- Input: numbers = [2,7,11,15], target = 9<br>Output: [1,2]
- Input: numbers = [2,3,4], target = 6<br>Output: [1,3]

</details>

```
class Solution {
   public int[] twoSum(int[] numbers, int target) {
        int[] res = new int[2];
        int i = 0;
        int j = numbers.length - 1;

        while (i < j) {
            if (numbers[i] + numbers[j] == target) {
                res[0] = i + 1;
                res[1] = j + 1;
                return res;
            } else if (numbers[i] + numbers[j] > target) {
                j--;
            } else {
                i++;
            }
        }
        return res;
    }
}
```

