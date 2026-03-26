# Attempting the Intermediate Question (Product of Array Except Self)

## LeetCode
<img width="1919" height="1022" alt="image" src="https://github.com/user-attachments/assets/c3141fab-76fd-492d-a402-0ae59a95b9be" />


## Code
```cpp
class Solution {
public:
    vector<int> productExceptSelf(vector<int>& nums) {
        vector<int> ans (nums.size(),1);
        int pre = 1;
        for (int i = 0; i < nums.size(); i++) 
        {
            ans[i] = pre;     
            pre *= nums[i];   
        }
        
        int post = 1;
        for (int i = nums.size() - 1; i >= 0; i--) 
        {
            ans[i] *= post;   
            post *= nums[i];  
        }
        
        return ans;
    }
};
```

## Approach
Two-pass prefix and suffix product strategy to avoid using the division operator. The first pass calculates the product of all elements to the left of each index, storing it directly in the output array. The second reverse pass calculates the product of all elements to the right on the fly, multiplying it against the stored left products to get the final answer.

## Complexities
TC = O(n)

SC = O(1) (excluding the output array, as specified in the question)

    
