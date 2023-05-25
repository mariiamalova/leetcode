# Path Crossing

[Task on leetcode](https://leetcode.com/problems/path-crossing/description/)

<details>
<summary>Task</summary>
Given a string path, where path[i] = 'N', 'S', 'E' or 'W', each representing moving one unit north, south, east, or west, respectively. You start at the origin (0, 0) on a 2D plane and walk on the path specified by path.

Return true if the path crosses itself at any point, that is, if at any time you are on a location you have previously visited. Return false otherwise.
</details>

<details>
<summary>Test Cases</summary>

- Input: path = "NES"<br>Output: false
- Input: path = "NESWW"<br>Output: true

</details>


```
class Solution {
   public boolean isPathCrossing(String path) {
        int x = 0;
        int y = 0;
        List<String> list = new ArrayList<>();
        list.add(x + "." + y);
        for (int i = 0; i < path.length(); i++) {
            switch (path.charAt(i)) {
                case ('N') : x += 1;
                    list.add(x + "." + y);
                break;
                case ('E') : y += 1;
                    list.add(x + "." + y);
                break;
                case ('S') : x -= 1;
                    list.add(x + "." + y);
                break;
                case ('W') : y -= 1;
                    list.add(x + "." + y);
                break;
            }
        }
        if (list.stream().distinct().count() < list.size()) {
            return true;
        }
    return false;
    }
}

```