# Long Pressed Name

[Task on leetcode](https://leetcode.com/problems/long-pressed-name/description/)
<details>
<summary>Task</summary>
Your friend is typing his name into a keyboard. Sometimes, when typing a character c, the key might get long pressed, and the character will be typed 1 or more times.

You examine the typed characters of the keyboard. Return True if it is possible that it was your friends name, with some characters (possibly none) being long pressed.
</details>
<details>
<summary>Test Cases</summary>

- Input: name = "alex", typed = "aaleex"<br>Output: true
- Input: name = "saeed", typed = "ssaaedd"<br>Output: false

</details>

```
class Solution {
     public boolean isLongPressedName(String name, String typed) {
        int n = name.length();
        int t = typed.length();
        int i = 0;
        int j = 0;
        
        if (n > t)
            return false;
        if (n == t && !name.equals(typed))
            return false;
        if (name.charAt(0) != typed.charAt(0))
            return false;
            
        while (i < n && j < t) {
            if (name.charAt(i) == typed.charAt(j)) {
                i++;
                j++;
            } else if (name.charAt(i - 1) == typed.charAt(j)) {
                j++;
            } else {
                return false;
            }
        }
        
        if (i != n) {
            return false;
        }
        
        if (j < t) {
            while (j < t) {
                if (name.charAt(i - 1) != typed.charAt(j)) {
                    return false;
                }
                j++;
            }
        }
        return true;
    }
}
```
