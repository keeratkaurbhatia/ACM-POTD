# Attempting the Intermediate Question (3Sum)

## LeetCode
<img width="1919" height="1019" alt="image" src="https://github.com/user-attachments/assets/08d44baa-91ce-4f1a-8236-d7bbe2bf82cd" />

## Code
```cpp
class Solution {
public:
    vector<vector<int>> threeSum(vector<int>& nums) {
        set<vector<int>> ans; //to avoid duplicate answers
        sort(nums.begin(),nums.end());
        for (int i = 0; i<nums.size()-2; i++)
        {
            //to skip duplicate in processing
            if(i>0 && nums[i]==nums[i-1])
            {
                continue;
            }
            int target = -nums[i];
            unordered_map<int,int> remember;
            for (int j = i+1; j<nums.size(); j++)
            {
                
                if (remember.find(nums[j])==remember.end())
                {
                    remember[target-nums[j]] = nums[j];
                }
                else
                {
                    ans.insert({nums[i],nums[j],remember[nums[j]]});
                }
            }
        }
        vector<vector<int>> final;
        for (vector<int> triplet : ans) 
        { 
            final.push_back(triplet);
        }
        return final;
    }
};
```

## Approach
A 2Sum type approach where the target sum becomes the negative of one of the numbers in the triplet, i.e. num[i] + nums[j] + nums[k] = 0 can be rewritten as num[i] + nums[j] = -nums[k]

## Complexities
TC = O(n^2)

SC = O(n)

    
