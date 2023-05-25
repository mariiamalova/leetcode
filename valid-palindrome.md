# Valid Palindrome

[Task on leetcode](https://leetcode.com/problems/valid-palindrome/description/)
<details>
<summary>Task</summary>
A phrase is a palindrome if, after converting all uppercase letters into lowercase letters and removing all non-alphanumeric characters, it reads the same forward and backward. Alphanumeric characters include letters and numbers.

Given a string s, return true if it is a palindrome, or false otherwise.
</details>
<details>
<summary>Test Cases</summary>

- Input: s = "A man, a plan, a canal: Panama"<br>Output: true
- Input: s = "race a car"<br>Output: false

</details>

```
class Solution {
    public boolean isPalindrome(String s) {
        s = s.toLowerCase()
                .replaceAll("\\s+", "")
                .replaceAll("\\p{Punct}", "");
        for (int i = 0, j = s.length() - 1; i < s.length() - 1 && j >= 0; i++, j--) {
                if (s.charAt(i) != s.charAt(j)) {
                    return false;
                }
            }
        return true;
    }
}
```
