# Shuffle String

[Task on leetcode](https://leetcode.com/problems/shuffle-string/description/)

<details>
<summary>Task</summary>
You are given a string "s" and an integer array indices same length. The string s will be shuffled such that the character at the i-th indices[i].
Return the shuffled string.
</details>

<details>
<summary>Test Cases</summary>

- Input: s = "codeleet", indices = [4,5,6,7,0,2,1,3]<br>Output: "leetcode"
- Input: s = "abc", indices = [0,1,2]<br>Output: "abc"

</details>

```
class Solution {
       public String restoreString(String s, int[] indices) {
     String a = "";
        for (int i = 0; i < indices.length; i++) {
            for (int j = 0; j < indices.length; j++) {
                if (indices[j]==i){
                    a += s.charAt(j);
                }
            }
        }
        return a;
    }
}
```