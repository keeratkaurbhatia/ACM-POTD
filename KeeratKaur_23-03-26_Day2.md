# Attempting the Intermediate Question (Subarray Sum Equals K)

## LeetCode
<img width="1919" height="1025" alt="image" src="https://github.com/user-attachments/assets/21570a1d-8832-4658-9162-22fddeb53fb6" />

## Code
```cpp
class Solution {
public:
    int subarraySum(vector<int>& nums, int k) {
        
        int count = 0;
        for (int left = 0; left<nums.size(); left++)
        {
            int sum = 0;
            for (int right = left; right<nums.size();right++)
            {
                sum+=nums[right];
                
                if(sum==k)
                {
                    count++;
                }
            }
        }
        return count;
    }
};
```

## Approach
A brute force approach to keep check whenever the sum becomes equal to the count. No early breaking of the loop to ensure negatives are accounted for i.e, a larger sum currently has the possibility of reducing and potentially achieving the required sum due to negative elements.

## Complexities
TC = O(n^2)

SC = O(1)

    
