# Attempting the Intermediate Question (Sort List)

## LeetCode
<img width="1919" height="1024" alt="image" src="https://github.com/user-attachments/assets/a1f4469b-101c-4cd6-ba96-c229810c5422" />

## Code
```cpp
/**
 * Definition for singly-linked list.
 * struct ListNode {
 * int val;
 * ListNode *next;
 * ListNode() : val(0), next(nullptr) {}
 * ListNode(int x) : val(x), next(nullptr) {}
 * ListNode(int x, ListNode *next) : val(x), next(next) {}
 * };
 */
class Solution {
public:
    ListNode* sortList(ListNode* head) {
        vector<int> arr={};
        ListNode* temp = head;
        while (temp)
        {
            arr.push_back(temp->val);
            temp=temp->next;
        }
        sort(arr.begin(),arr.end());
        temp = head;
        for (int i: arr)
        {
            temp->val=i;
            temp=temp->next;
        }
        return head;
    }
};
```

## Approach
An array-based replacement approach. We first traverse the entire linked list and store the values of each node into a standard array (vector). We then sort this array using the built-in `sort()` function. Finally, we traverse the linked list a second time, sequentially overwriting the existing node values with the newly sorted values from our array. 

## Complexities
TC = O(n log n) *(O(n) to traverse the list twice + O(n log n) for the built-in sorting algorithm)*

SC = O(n) *(For storing the 'n' elements of the linked list inside the vector)*
