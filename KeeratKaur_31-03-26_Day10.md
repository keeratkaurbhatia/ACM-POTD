# Attempting the Intermediate Question (Add Two Numbers)

## LeetCode
<img width="1919" height="958" alt="image" src="https://github.com/user-attachments/assets/17875ce2-c3fb-4b19-8857-c6c8d07ecff2" />


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
    ListNode* addTwoNumbers(ListNode* l1, ListNode* l2) {
        ListNode dummy{0};
        auto curr = &dummy;

        auto carry = 0;
        while (l1 || l2 || carry) {
            auto a = l1 ? l1->val : 0, b = l2 ? l2->val : 0;
            auto val = carry + a + b;
            curr->next = new ListNode(val % 10);
            carry = val / 10;
            l1 = l1 ? l1->next : nullptr;
            l2 = l2 ? l2->next : nullptr;
            curr = curr->next;
        }

        return dummy.next;
    }
};
```

## Approach
Initialize a dummy head node to simplify the creation of the output list, and use a curr pointer to keep track of the current tail. Iterate through l1 and l2 simultaneously while either list has remaining nodes or there is an active carry value. In each step, sum the values from l1, l2, and the carry. Add a new node to the result list with the digit val % 10, then update the carry to val / 10 for the next iteration. Move the l1 and l2 pointers forward if they haven't reached the end. Once all nodes and carries are processed, return dummy.next.

## Complexities
TC = O(max(m, n)) Where m and n are the lengths of l1 and l2 respectively. 

SC = O(1) auxiliary space  
