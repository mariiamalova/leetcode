# String Compression



[Task on leetcode](https://leetcode.com/problems/string-compression/)
<details>
<summary>Task</summary>
Given an array of characters chars, compress it using the following algorithm:

Begin with an empty string s. For each group of consecutive repeating characters in chars:

- If the group's length is 1, append the character to s.
- Otherwise, append the character followed by the group's length.
  
The compressed string s should not be returned separately, but instead, be stored in the input character array chars. Note that group lengths that are 10 or longer will be split into multiple characters in chars.
After you are done modifying the input array, return the new length of the array.
You must write an algorithm that uses only constant extra space.

</details>
<details>
<summary>Test Cases</summary>

- Input: ["a","a","b","b","c","c","c"]<br>Output: ["a","2","b","2","c","3"]  
- Input: ["a","b","b","b","b","b","b","b","b","b","b","b","b"]<br>Output: ["a","b","1","2"]

</details>

```
class Solution {
 public String compress(char[] chars) {
        if (chars.length == 1) {
            return String.valueOf(chars[0]);
        }
        int count = 1;
        StringBuilder newChars = new StringBuilder();
        for (int i = 0; i < chars.length - 1; i++) {
            if (chars[i] == chars[i + 1]) {
                count++;
                if (i == chars.length - 2) {
                    newChars.append(chars[i]);
                    newChars.append(count);
                    count = 1;
                }
            } else if (i == chars.length - 2) {
                if (count != 1) {
                    newChars.append(chars[i])
                            .append(count)
                            .append(chars[i + 1]);
                } else {
                    newChars.append(chars[i])
                            .append(chars[i + 1]);
                }
            } else {
                newChars.append(chars[i]);
                if (count != 1) {
                    newChars.append(count);
                    count = 1;
                }
            }
        }
        return newChars.toString();
    }
 }
```
