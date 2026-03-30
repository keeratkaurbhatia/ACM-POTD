# Attempting the Intermediate Question (Linked List Cycle II)

## LeetCode
<img width="1919" height="1025" alt="image" src="https://github.com/user-attachments/assets/0e7cbcdb-da94-4919-80b5-7d578b7a49d5" />

## Code
```cpp
/**
 * Definition for singly-linked list.
 * struct ListNode {
 * int val;
 * ListNode *next;
 * ListNode(int x) : val(x), next(NULL) {}
 * };
 */
class Solution {
public:
    ListNode *detectCycle(ListNode *head) {
        ListNode *temp = head;
        unordered_set<ListNode*> seen;
        while (temp != NULL) 
        {
            if (seen.find(temp) != seen.end()) 
            {
                return temp; // cycle found
            }
            seen.insert(temp);
            temp = temp->next;
        }
        return temp; // reached end, no cycle
    }
};
```

## Approach
Traverse the linked list while storing each visited node in a hash set (`unordered_set`). Before inserting a node, check if it already exists in the set. If it does, we have found the start of the cycle and can return that node. If we reach the end of the list (`NULL`), it means there is no cycle.

## Complexities
TC = O(n)

SC = O(n)
