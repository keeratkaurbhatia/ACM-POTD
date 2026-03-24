# Attempting the Intermediate Question (Sort Colors)

## LeetCode
<img width="1915" height="1012" alt="image" src="https://github.com/user-attachments/assets/f899f02d-e914-4814-867b-ce86ff0751d7" />

## Code
```cpp
class Solution {
public:
    void sortColors(vector<int>& nums) {
        int start = 0;
        int end = nums.size()-1;
        int i = 0;
            while(i<=end)
            {
                if(nums[i]==2)
                {
                    swap(nums[i],nums[end]);
                    end--;
                }
                else if (nums[i]==0)
                {
                    swap(nums[i],nums[start]);
                    start++;
                    i++;
                }
                else i++;
            }
        
    }
};
```

## Approach
Maintain 2 pointers to swap 2's to the end and 0's to the front. In doing so, the 1's will automatically come in the middle.

## Complexities
TC = O(n)

SC = O(1)

    
