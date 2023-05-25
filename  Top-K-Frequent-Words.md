# Top K Frequent Words
[Task on leetcode](https://leetcode.com/problems/top-k-frequent-words/description/)

<details>
<summary>Task</summary>
Given an array of strings words and an integer k, return the k most frequent strings.

Return the answer sorted by the frequency from highest to lowest. Sort the words with the same frequency by their lexicographical order.
</details>

<details>
<summary>Test Cases</summary>

- Input: words = ["i","love","leetcode","i","love","coding"], k = 2<br>Output: ["i","love"]
- Input: words = ["the","day","is","sunny","the","the","the","sunny","is","is"], k = 4<br>Output: ["the","is","sunny","day"]

</details>

```
class Solution {
    public List<String> topKFrequent(String[] words, int k) {
        return Arrays.stream(words)
        .collect(Collectors.groupingBy(Function.identity(), Collectors.counting()))
                .entrySet()
                .stream()
                .sorted(Map.Entry.comparingByKey())
                .sorted(Map.Entry.comparingByValue(Comparator.reverseOrder()))
                .map(Map.Entry::getKey)
                .limit(k)
                .toList();
    }
}
```
