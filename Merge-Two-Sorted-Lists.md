# Merge Two Sorted Lists

[Task on leetcode](https://leetcode.com/problems/move-zeroes/description/)

<details>
<summary>Task</summary>
You are given the heads of two sorted linked lists list1 and list2.
Merge the two lists in a one sorted list. The list should be made by splicing together the nodes of the first two lists.
Return the head of the merged linked list.
</details>

<details>
<summary>Test Cases</summary>

- Input: list1 = [1,2,4], list2 = [1,3,4]<br>Output: [1,1,2,3,4,4]
- Input: list1 = [], list2 = []<br>Output: []

</details>

```
/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode() {}
 *     ListNode(int val) { this.val = val; }
 *     ListNode(int val, ListNode next) { this.val = val; this.next = next; }
 * }
 */
class Solution {
     public ListNode mergeTwoLists(ListNode list1, ListNode list2) {
        ListNode result = new ListNode();
        if (list1 == null) {
            return list2;
        }
        if (list2 == null) {
            return list1;
        }

        if (list1.val <= list2.val) {
            result.val = list1.val;
            result.next = mergeTwoLists(list1.next, list2);

        } else {
            result.val = list2.val;
            result.next = mergeTwoLists(list1, list2.next);
        }

        return result;
    }
}
```
