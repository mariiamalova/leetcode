# Group Anagrams

[Task on leetcode](https://leetcode.com/problems/group-anagrams/description/)

<details>
<summary>Task</summary>
Given an array of strings strs, group the anagrams together. You can return the answer in any order.

An Anagram is a word or phrase formed by rearranging the letters of a different word or phrase, typically using all the original letters exactly once.</details>

</details>
<details>
<summary>Test Cases</summary>

- Input: strs = ["eat","tea","tan","ate","nat","bat"]<br>Output: [["bat"],["nat","tan"],["ate","eat","tea"]]
- Input: strs = ["a"]<br>Output: [["a"]]

</details>

```
class Solution {
     public List<List<String>> groupAnagrams(String[] strs) { 
        Map<String, List<String>> map = new HashMap<>();
        List<List<String>> res = new ArrayList<>();

        for (String str : strs) {

            char[] chars = str.toCharArray();
            Arrays.sort(chars);
            String sortString = String.valueOf(chars);

            List<String> list = map.getOrDefault(sortString,
                    new ArrayList<>());

            list.add(str);
            map.put(sortString, list);
        }
        for (Map.Entry e : map.entrySet()){
        res.add((List<String>) e.getValue());
        }
        return res;
    }
}
```